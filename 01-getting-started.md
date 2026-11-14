---
title: Getting started with Kitrise
---

# Getting started with Kitrise

Kitrise 1.0.0 by digimaps.co is a Shopify Online Store 2.0 theme. This page covers install, first setup and where each template lives.

## Install

1. In Shopify admin, open **Online Store > Themes**.
2. Add the Kitrise theme (from the Theme Store, or upload the theme zip).
3. Click **Customize** to open the theme editor. Publish when you are ready.

## What a clean install looks like

A clean install has the theme layout and sections, but no store content.

- No products, collections, blog posts, pages, images or videos are preselected in any template. Sections that need them stay empty until you pick them.
- The templates carry placeholder text only (headings, button labels, captions). Replace it with your own copy.
- The header uses the menu handle `main-menu` for **Main menu** and **Search shortcuts**. The footer ships with three **Footer menu** blocks: Shop uses `main-menu`, Support uses `footer`, and About has no menu selected. If your store has no menu with those handles, create them under **Content > Menus**, or pick another menu in the section settings.

## Demo theme vs clean install

The demo theme is a Kitrise preview with products, images and menus filled in so every section can be seen. A clean install is the same code without that store data. Your products, collections and menus are yours to add. Nothing in the theme code depends on demo data.

## Recommended first steps

Work through these steps in the theme editor.

1. **Logo.** Open the Header section. Set **Logo on light backgrounds** (use a dark logo). Optionally set **Logo on dark / transparent backgrounds** and **Text logo fallback**. Adjust **Logo width** and **Mobile logo width**. The footer has its own logo settings (**Logo (default)**, **Logo (dark background)**) and a **Brand display** choice.
2. **Favicon.** Theme settings > **Brand** > **Favicon**.
3. **Colors.** Theme settings > **Colors**: Text, Background, Secondary background, Secondary background text, Accent, Highlight, Highlight text, Accent text. For a dark appearance, use **Color mode**: **Enable light and dark mode**, **Default appearance**, and the dark color settings.
4. **Typography.** Theme settings > **Typography**: **Body font**, **Body size**, **Additional body text scaling**, **Heading font**, **Heading size**.
5. **Menus.** Create `main-menu` and `footer` in **Content > Menus**. In the Header, check **Main menu** and **Search shortcuts**. In the Footer, add or edit **Footer menu** blocks and set **Footer menu** and **Heading**.
6. **Home page.** Open the Home page in the editor. It ships with these sections, in order: Hero, Media collections, Collection tabs, Jersey customizer, Image comparison, Media collections, Bundle builder, Campaign showcase, Hotspots, Lifestyle showcase, Video, Blog posts, Icon benefits. Pick collections, images and products in each one. Remove sections you do not need.
7. **Other settings worth a look.** Layout (**Page width**), Shapes, Product cards, Cart (**Cart type**), and Social media.

## Where to find each template

Open the page type in the theme editor preview selector.

| Template | Used for | Main section |
| --- | --- | --- |
| `index` | Home page | See step 6 |
| `collection`, `collection.sport` | Collection pages | Collection page |
| `list-collections` | All collections | Collection index |
| `product`, `product.gallery`, `product.gift-card`, `product.jersey` | Product pages | Product information (Jersey customizer on `product.jersey`) |
| `cart` | Cart page | Cart |
| `search` | Search results | Search results |
| `blog`, `article` | Blog and posts | Blog listing, Blog article |
| `page`, `page.about`, `page.care`, `page.contact`, `page.faq`, `page.orders`, `page.showcase`, `page.sport`, `page.teamwear`, `page.jersey-studio` | Pages. Pick the template on the page in Shopify admin. | Page content, FAQ, Contact form and others |
| `customers/*` (account, login, register, addresses, order, reset and activate password) | Customer accounts | Customer account |
| `password` | Password page | Password page |
| `gift_card.liquid` | Gift card page | Standalone template |
| `404` | Not found | 404 page |

The header and footer live in two section groups: **Header group** (Announcement bar and Header) and **Footer** (Footer and Welcome popup).
