---
name: salla-docs
description: Comprehensive Salla e-commerce platform documentation. Use this skill when working with Salla APIs (products, orders, shipping, customers, payments, taxes, coupons, store settings, webhooks), Salla storefront JavaScript modules (auth, cart, product, currency, events, forms, ratings, wishlists), Twilight/Twig theme development (layouts, pages, components, file structure), Salla app development (OAuth, app functions, CLI commands, review process), or any Salla-related integration question.
---

# Salla Documentation

## Overview

This skill provides the complete Salla e-commerce platform documentation, consolidated from 676 source pages into per-topic reference files. Each file is sized for single-read loading (under 2000 lines where possible).

## How to Find the Right Reference File

Reference files are in `references/`. File names follow the pattern `{topic}.md` or `{topic}--{subtopic}.md`.

**To find the right file:** Use the Glob tool with a pattern matching the topic keyword:
```
Glob: references/apis-products*.md    → all product API files
Glob: references/theme-*.md           → all theme files
Glob: references/apis-order*.md       → all order API files
```

Then Read the matching file. For files over 2000 lines (some API endpoint specs), use Grep to find the relevant section first, then Read with offset/limit.

## Reference File Index

### Product APIs
| Files | Content |
|---|---|
| `apis-products--*.md` | CRUD products, list, search, bulk actions, SKU operations |
| `apis-product-variants--*.md` | Product variants |
| `apis-product-options--*.md` | Product options |
| `apis-product-option-values--*.md` | Option values |
| `apis-product-option-templates--*.md` | Option templates |
| `apis-product-images--*.md` | Product images, YouTube videos |
| `apis-product-quantity--*.md` | Quantity, audit, digital codes, tags |

### Order APIs
| Files | Content |
|---|---|
| `apis-orders--*.md` | CRUD orders, list, duplicate, draft, relocate stock |
| `apis-order-status--*.md` | Order statuses, custom statuses, bulk update |
| `apis-order-items--*.md` | Order items, histories, reservations |
| `apis-order-options--*.md` | Order options |
| `apis-order-invoice--*.md` | Invoices |
| `apis-order-assignment.md` | Order assignment |

### Shipping APIs
| Files | Content |
|---|---|
| `apis-shipments--*.md` | CRUD shipments, cancel, return |
| `apis-shipping-companies--*.md` | Shipping companies |
| `apis-shipping-routes--*.md` | Shipping routes |
| `apis-shipping-zones--*.md` | Shipping zones |
| `shipments--*.md` | Merchant shipment operations |
| `shipping-routes--*.md` | Merchant shipping routes |
| `shipping-management.md` | Shipping management, AWB generation |

### Customer APIs
| Files | Content |
|---|---|
| `apis-customers--*.md` | CRUD customers, ban, import |
| `apis-customer-groups--*.md` | Customer groups |
| `apis-customer-wallet.md` | Customer wallet, loyalty points |

### Commerce APIs
| Files | Content |
|---|---|
| `apis-coupons--*.md` | Coupons, coupon codes |
| `apis-special-offers--*.md` | Special offers |
| `apis-transactions--*.md` | Transactions, payment methods |
| `apis-taxes.md` | Taxes |
| `settlements.md` | Settlements |

### Store Management APIs
| Files | Content |
|---|---|
| `apis-branches--*.md` | Branches |
| `apis-branches-allocations--*.md` | Branch allocations |
| `apis-branch-delivery-zones--*.md` | Branch delivery zones |
| `apis-brands--*.md` | Brands |
| `apis-categories--*.md` | Categories |
| `apis-settings.md` | Store settings |
| `apis-merchant--*.md` | Merchant info, employees, store scopes, SEO |
| `apis-exports--*.md` | Data exports |

### Other APIs
| Files | Content |
|---|---|
| `apis-advertisements--*.md` | Advertisements, abandoned carts |
| `apis-affiliates--*.md` | Affiliates |
| `apis-countries.md` | Countries, cities, districts |
| `apis-currencies--*.md` | Currencies, languages |
| `apis-dns-records.md` | DNS records, custom URLs |
| `apis-feedbacks--*.md` | Feedbacks, reviews |
| `apis-webhooks.md` | Webhook API endpoints |

### Storefront SDK (JavaScript)
| Files | Content |
|---|---|
| `auth.md` | Authentication module |
| `cart.md` | Cart operations |
| `product.md` | Product display, gifted products, product card |
| `elements.md` | UI elements |
| `events.md` | Event system |
| `form.md` | Form handling |
| `user.md` | User module |
| `order-fulfilment.md` | Order fulfilment, order display |
| `rating.md` | Ratings |
| `storefront-misc.md` | Booking, currency, comments, loyalty, wishlist, profile, subscriptions |

### Theme Development (Twilight/Twig)
| Files | Content |
|---|---|
| `theme-architecture-layouts.md` | Layouts, base architecture |
| `theme-architecture-components.md` | Component overview |
| `theme-architecture-components-home-components.md` | Home page components |
| `theme-architecture-components-common-components.md` | Common components, product components |
| `theme-architecture-pages-*.md` | Pages: common, customer, product, blog, brand |
| `twig-template-engine.md` | Twig template syntax |
| `twilight-themes-command.md` | Twilight CLI commands |
| `files-and-folders-structure.md` | Project file structure |

### App Development
| Files | Content |
|---|---|
| `app-details-builder-components.md` | App details builder |
| `app-functions.md` | App functions |
| `apps-command.md` | CLI commands |
| `requirements-and-review-review-process.md` | App review process |

### Webhooks & Events
| Files | Content |
|---|---|
| `webhooks-store-events--*.md` | Store webhook events |
| `merchants-events--*.md` | Merchant events, customer events |

### Getting Started & General
| Files | Content |
|---|---|
| `getting-started.md` | Getting started guides, API overview, additional resources |
| `docs--*.md` | API changelog, rate limiting, webhooks guide, app functions guide, theme architecture overview |
| `learn-what-you'll-learn--*.md` | Learning resources |

## Scripts

- `scripts/consolidate.py` — Rebuilds all reference files from the raw `docs/` directory. Run if source docs are updated.
