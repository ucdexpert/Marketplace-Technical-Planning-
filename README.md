# Marketplace-Technical-Planning-


export default {
  name: 'homepage',
  type: 'document',
  title: 'Homepage',
  fields: [
    {
      name: 'heroSection',
      type: 'object',
      title: 'Hero Section',
      fields: [
        {
          name: 'heading',
          type: 'string',
          title: 'Hero Heading',
          validation: (Rule) => Rule.required().error('Hero heading is required.'),
        },
        {
          name: 'subHeading',
          type: 'string',
          title: 'Hero Subheading',
          validation: (Rule) => Rule.required().max(150).error('Subheading is required and cannot exceed 150 characters.'),
        },
        {
          name: 'ctaText',
          type: 'string',
          title: 'CTA Button Text',
          validation: (Rule) => Rule.required().error('CTA text is required.'),
        },
        {
          name: 'heroImage',
          type: 'image',
          title: 'Hero Image',
          options: { hotspot: true },
          validation: (Rule) => Rule.required().error('Hero image is required.'),
        },
      ],
    },
    {
      name: 'partners',
      type: 'array',
      title: 'Partner Logos',
      of: [
        {
          type: 'image',
          title: 'Partner Logo',
          options: { hotspot: true },
          validation: (Rule) => Rule.required().error('Each partner logo must include an image.'),
        },
      ],
    },
    {
      name: 'featuredProducts',
      type: 'array',
      title: 'Featured Products',
      of: [
        {
          type: 'object',
          title: 'Product',
          fields: [
            {
              name: 'name',
              type: 'string',
              title: 'Product Name',
              validation: (Rule) => Rule.required().error('Product name is required.'),
            },
            {
              name: 'price',
              type: 'number',
              title: 'Price',
              validation: (Rule) => Rule.required().min(0).error('Product price must be provided.'),
            },
            {
              name: 'image',
              type: 'image',
              title: 'Product Image',
              options: { hotspot: true },
              validation: (Rule) => Rule.required().error('Product image is required.'),
            },
          ],
        },
      ],
    },
    {
      name: 'categories',
      type: 'array',
      title: 'Top Categories',
      of: [
        {
          type: 'object',
          title: 'Category',
          fields: [
            {
              name: 'title',
              type: 'string',
              title: 'Category Name',
              validation: (Rule) => Rule.required().error('Category name is required.'),
            },
            {
              name: 'image',
              type: 'image',
              title: 'Category Image',
              options: { hotspot: true },
              validation: (Rule) => Rule.required().error('Category image is required.'),
            },
          ],
        },
      ],
    },
    {
      name: 'exploreSection',
      type: 'object',
      title: 'Explore Section',
      fields: [
        {
          name: 'title',
          type: 'string',
          title: 'Section Title',
          validation: (Rule) => Rule.required().error('Explore section title is required.'),
        },
        {
          name: 'images',
          type: 'array',
          title: 'Explore Images',
          of: [
            {
              type: 'image',
              title: 'Image',
              options: { hotspot: true },
            },
          ],
          validation: (Rule) => Rule.required().min(1).error('At least one image is required.'),
        },
      ],
    },
    {
      name: 'products',
      type: 'array',
      title: 'Our Products',
      of: [
        {
          type: 'object',
          title: 'Product',
          fields: [
            {
              name: 'name',
              type: 'string',
              title: 'Product Name',
              validation: (Rule) => Rule.required().error('Product name is required.'),
            },
            {
              name: 'price',
              type: 'number',
              title: 'Product Price',
              validation: (Rule) => Rule.required().error('Product price is required.'),
            },
            {
              name: 'image',
              type: 'image',
              title: 'Product Image',
              options: { hotspot: true },
              validation: (Rule) => Rule.required().error('Product image is required.'),
            },
          ],
        },
      ],
    },
    {
      name: 'footer',
      type: 'object',
      title: 'Footer',
      fields: [
        {
          name: 'logo',
          type: 'image',
          title: 'Footer Logo',
          options: { hotspot: true },
          validation: (Rule) => Rule.required().error('Footer logo is required.'),
        },
        {
          name: 'links',
          type: 'array',
          title: 'Footer Links',
          of: [
            {
              type: 'object',
              fields: [
                {
                  name: 'label',
                  type: 'string',
                  title: 'Link Label',
                  validation: (Rule) => Rule.required().error('Link label is required.'),
                },
                {
                  name: 'url',
                  type: 'url',
                  title: 'Link URL',
                  validation: (Rule) => Rule.required().error('Link URL is required.'),
                },
              ],
            },
          ],
        },
        {
          name: 'socialMedia',
          type: 'array',
          title: 'Social Media Links',
          of: [
            {
              type: 'object',
              fields: [
                {
                  name: 'platform',
                  type: 'string',
                  title: 'Platform Name',
                },
                {
                  name: 'url',
                  type: 'url',
                  title: 'Platform URL',
                },
              ],
            },
          ],
        },
      ],
    },
  ],
};
