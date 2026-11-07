# Shopify Liquid Snippets

Small, copy-paste Liquid snippets I keep reusing on Shopify theme projects. Each one fixes something that comes up again and again in audits: slow hero images, fonts blocking text, and missing structured data.

They work with Online Store 2.0 themes (Dawn and most themes built on it).

## Snippets

| Snippet | What it does |
| --- | --- |
| [`responsive-image.liquid`](snippets/responsive-image.liquid) | Responsive `<img>` with `widths` + `sizes`, lazy by default, and eager + `fetchpriority="high"` + preload for the LCP image |
| [`font-preload.liquid`](snippets/font-preload.liquid) | Preloads the one font file used above the fold |
| [`product-json-ld.liquid`](snippets/product-json-ld.liquid) | `Product` structured data with an `Offer` for every variant |
| [`breadcrumb-json-ld.liquid`](snippets/breadcrumb-json-ld.liquid) | `BreadcrumbList` structured data for product and collection pages |
| [`organization-json-ld.liquid`](snippets/organization-json-ld.liquid) | `Organization` structured data for the home page |

## How to use

1. Copy the file into your theme's `snippets/` folder.
2. Render it where you need it, for example:

```liquid
{% render 'responsive-image', image: section.settings.image, eager: true %}
```

Each file has usage notes at the top.

## Before you ship

- Work on a duplicate theme, not the live one.
- Only one image per page should be `eager: true`. Preloading several images makes things slower, not faster.
- If your theme or an SEO app already outputs `Product` or `BreadcrumbList` JSON-LD, remove the duplicate. Two blocks for the same thing can confuse Google.
- Test structured data with Google's [Rich Results Test](https://search.google.com/test/rich-results) and speed with [PageSpeed Insights](https://pagespeed.web.dev/).

## Contributing

Found a bug or have a snippet that belongs here? Open an issue or a pull request.

## Author

Maintained by [Raunak Singh](https://raunaksingh.co.in/shopify-developer), Shopify and Next.js developer.

Related write-up: [7 Shopify Liquid Fixes That Cut LCP on Real Stores](https://dev.to/raunaksingh/7-shopify-liquid-fixes-that-cut-lcp-on-real-stores-g22)

## License

MIT
