---
title: Products, variants and metafields
---

# Products, variants and metafields

Kitrise by digimaps.co. This guide covers the product page, variant images, color swatches, sibling products, pricing details, pickup, payment terms, recommendations, the gift card flow and filters.

All labels below are the exact names shown in the theme editor.

## 1. Product page blocks

The product page template is `templates/product.json`. It holds two sections:

1. **Product information** (the main section). All the blocks below live here.
2. **Related products**, placed after it.

### Available blocks

| Block | Limit | What it does |
| --- | --- | --- |
| App blocks | any | Lets you add app blocks. |
| Product type | 1 | Shows the product type as a tag. |
| Vendor | 1 | Always shows the product vendor. |
| Product heading | 1 | Product title. Settings: **Show vendor** (used only when there is no Vendor block), **Show SKU** (used only when there is no SKU block). |
| SKU | 1 | Shows the SKU of the selected variant. |
| Price | 1 | Price, compare-at price, sale badge, unit price, and the taxes and shipping policy notes. |
| Variant picker | 1 | One option group per product option. |
| Quantity selector | 1 | Quantity input. |
| Buy buttons | 1 | Add to bag, accelerated checkout, purchase options (selling plans), gift card recipient form, pickup availability, payment terms, size guide. Settings: **Show accelerated checkout**, **Size guide page**, **Show gift card recipient form**, **Show local pickup availability**. |
| Product options and purchase (classic) | 1 | Older all-in-one block that combines variant picker, quantity and buy buttons. Use Variant picker, Quantity selector and Buy buttons for new setups. |
| Product features | 1 | Up to three icon, heading and short text items. |
| Complete the kit | 10 | Recommendation group. See section 8. |
| Description | 1 | Product description. Settings: **Show description as an accordion**, **Heading**, **Open by default**. |
| Text note | any | A rich text note. |
| Collapsible information | any | Accordion row. Settings: **Heading**, **Content source** (Custom text and page, Description, Selected page), **Content**, **Page content**, **Open by default**. |
| Custom Liquid | any | Your own Liquid code. |

Blocks Product features, Complete the kit, Text note and Collapsible information also have **Visibility** (All products / collections, or Selected collections only) and **Show for collections**. With Selected collections only, the block is hidden when no collection is selected. On the Buy buttons block, the same two settings control only where the size guide link shows.

### Block order

Blocks render in the order they appear in the theme editor. Drag to reorder.

The default template uses this order:

1. Product type
2. Vendor
3. Product heading
4. Price
5. Variant picker
6. Quantity selector
7. Buy buttons
8. Complete the kit group with the heading "You may also like." (Shopify complementary products)
9. Product features
10. Description
11. Collapsible information: Shipping and returns (set to Selected page; it shows once you pick a page), Fit and sizing, Materials and care

Notes on how order works:

- A Quantity selector placed directly before Buy buttons sits inside the product form. In any other position it still works and is linked to the form.
- A Complete the kit group set to **Below the buy buttons** always prints right after the Buy buttons block, whatever its place in the list. Only **Custom block position** follows the block order.
- **Product details placement** (section setting, shown when Gallery position is Left or Right) can move Description, Product features, Text note and Collapsible information to **Below the product images** on desktop. Only blocks placed after the last purchase block (Variant picker, Quantity selector, Buy buttons) move. On mobile they follow the buying options.

### Section settings

**Layout:** Gallery position (Left, Right, Above product information), Product details placement, Desktop gallery (Classic thumbnails, One image carousel, Two-column grid, First image full width, then pairs, Gentle continuous flow), Mobile gallery (One image carousel, Two image carousel, One image per row, Gentle continuous flow), Move images automatically, Flow speed (shown only when Move images automatically is on), Show denomination card design (gift cards only), Use global product image fit, Image fit, Use global product media radius, Image corner radius, Image ratio (Square, Portrait, Landscape), Keep details visible while scrolling.

**Content:** Show breadcrumb navigation, Show compact sticky cart bar.

**Appearance:** Color palette, Top spacing, Bottom spacing.

**Advanced:** Show advanced settings (reveals Column gap).

**Move images automatically** is off by default. Turn it on and the Gentle continuous flow gallery moves by itself, at the speed set in **Flow speed**, which only shows when this is on. It has no effect on the other gallery layouts. It does not start for visitors who ask their device to reduce motion, or when the product media includes anything other than images.

Theme-wide product image look is set in Theme settings > Product media (Product media background, Product image fit, Blend product images into their background). The gallery corner radius follows **Media corner radius** in Theme settings > **Shapes** while **Use global product media radius** is on. Turn it off to set **Image corner radius** for this section only. The **Featured product** section has the same two settings and **Move images automatically**.

## 2. Variant images

Each color (or any) variant can show its own image.

1. In Shopify admin, open the product.
2. In the variants list, click the variant, then the image slot, and choose the image for that variant. Do this for every color variant.
3. Save.

What the theme does:

- On first load, the gallery opens on the selected variant's image. If the variant has none, it opens on the product's featured image.
- When a customer picks another option, the gallery moves to that variant's image without a page reload.
- Product gallery shows all product media (images, video, external video, 3D models) in the layout you chose.

Tip: assign one image per color. Variants that share a color can share the same image.

## 3. Swatches

### Variant picker swatches (product page)

The Variant picker shows each option value as a button, so sizes and other options appear as buttons. A color value shows a swatch with the color name. A swatch is drawn when the option value has one:

- If you set a swatch image on the option value in Shopify, the theme shows the image.
- If you set a swatch color, the theme shows that color.
- If there is no swatch and the option is named **Color**, the theme looks the value up in a small built-in list: Forest, Olive, Ocean, Chalk, Black, White, Grey or Gray, Navy, Red (plus Turkish names Siyah, Beyaz, Gri, Lacivert, Kirmizi). Other names show text only.

To control swatch colors yourself, set swatches on the option values in Shopify admin. This is the most reliable method.

### Card swatches (collection, search and recommendation cards)

Product cards show up to **5** color dots. Theme settings > Product cards controls them:

- **Card color options:** Color swatches, Image thumbnails, None.
- **Color option action:** Preview on card (picking a dot swaps image, title, price and links on the card), or Open product.

Dot colors come from the option swatch color when set. Otherwise the theme uses its built-in color name table (for example Forest, Olive, Ocean, Cobalt, Graphite, Clay, Burgundy, Violet, Chalk, Black, White, Grey, Navy, Red, Blue, Green, Beige, Brown, Cream, Yellow, Orange, Pink, Purple, plus common Turkish names). A name that is not in the table gets an empty white ring, so set a swatch color for custom names.

### Kit tag on product cards and cart lines

Theme settings > **Product cards** > **Show kit label** (`card_show_kit_label`, on by default). Help text: "Shows the product type on every product and a print-ready note on jersey products."

When it is on, the card of every product that has a **Product type** shows a small sewn-label tag over the product image with that type. A product that uses the `jersey` template also gets a second accent tag that reads "Print-ready", for example "Home kit" and "Print-ready". The text comes from the **Product type** field of the product in Shopify admin, so fill it with the kit kind (Home kit, Away kit, Training kit and so on). If the field is empty, no tag is shown at all, including "Print-ready". Products without a product type show no tag.

In the cart, a kit line (a product on the `jersey` template, or a line with the hidden jersey properties) shows the product type as the same tag above the product title, without the "Print-ready" tag. This tag in the cart does not depend on **Show kit label**.

## 4. Sibling products (custom.sibling_products)

Use this when each color is its own product (for example "Jacket Forest" and "Jacket Olive") and you want the cards to show them as color dots of one product.

### Create the metafield

1. Shopify admin > Settings > Custom data > Products > **Add definition**.
2. Name: `Sibling products`. Namespace and key: `custom.sibling_products`.
3. Type: **Product**, with **List of products** turned on.
4. Save.

### Fill it

On each product in the group, open the metafield and select all products in the group, **including the product itself**. Do this on every product of the group so each card shows the same dots.

### What the theme does

- If the metafield has **more than one** product, the card shows one dot per product (max 5) and treats them as a group.
- Dot label and color: the theme reads the product's **Color** (or Colour, Renk) option value. If there is no color option, it uses the product title. The dot color comes from the built-in color table above.
- The dot for the product that owns the card is marked as current.
- On a collection page, siblings that are not in the same collection are skipped. The card's own product always stays.
- If `custom.sibling_products` is empty, the theme reads an older metafield namespace kept so existing data keeps working. New stores should use `custom.sibling_products` only.
- If neither metafield has more than one product, the card uses the product's own Color option values instead.

Sibling colors appear on product cards and in the Color row of the product page Variant picker. On the product page, the product's own color stays selected and each sibling links to its own product page with the same size (or other non-color choices) selected when that product has it.

## 5. Unit price display

Set it up in Shopify admin:

1. Open the variant, and under pricing turn on **Show unit price** (wording can vary by admin version).
2. Enter the **Total quantity** and **Unit** (for example 750 ml).
3. Save.

On the product page, the Price block prints a small line under the price: `unit price / reference unit` (for example `$4.00 / 100ml`). The reference quantity is hidden when it is 1. The line follows the selected variant and the selected purchase option. It appears only when the variant has a unit price measurement.

## 6. Pickup availability

Turn on local pickup in Shopify admin (Settings > Shipping and delivery > Local pickup) and enable pickup on the locations that offer it.

In the theme editor, open the Buy buttons block and check **Show local pickup availability** (on by default).

What shows:

- A summary line under the buttons: **Pickup available at** the first location that has the selected variant, with the pickup time, or **Pickup currently unavailable at** the location when none has it.
- A disclosure under the summary, labeled **View store information** (one location) or **Check availability at other stores** (several), listing each pickup location with its name, whether it is **Available for pickup** (with the pickup time) or not, and its address.
- Both update when the customer changes variant.
- Nothing shows when no pickup location stocks the selected variant.

In the product gallery, thumbnails of videos and 3D models carry a small play or 3D mark so shoppers can tell them from images.
- It is never shown for gift cards.

## 7. Payment terms

The theme prints Shopify's payment terms banner (Shop Pay Installments) inside the product form, below the buttons. It appears only when Shop Pay Installments is available for your store and the product. There is no theme setting for it. It refreshes when the variant changes.

Accelerated checkout buttons use the Buy buttons setting **Show accelerated checkout** (on by default). They show only for available variants, and not on gift card products while **Show gift card recipient form** is on.

## 8. Complementary and related recommendations (Search & Discovery)

### Install and configure the app

1. Install **Shopify Search & Discovery** from the Shopify App Store.
2. Open it and go to **Recommendations**.
3. For complementary products, open **Complementary products**, pick a product, and add its complements. Save.
4. For related products, Shopify generates them automatically. You can use the app to exclude products.

### Complete the kit block (complementary)

Add or edit a **Complete the kit** block in Product information. You can add up to 10 groups.

Settings:

- **Visibility** and **Show for collections**: the first group whose collections match the product is used. A group set to All products is the fallback. Groups with an empty source are skipped. Reorder groups to change priority.
- **Heading**
- **Source:** Selected products, Collection, Shopify complementary products, Selected + Shopify complementary.
  - Shopify complementary products uses what you set in Search & Discovery.
  - Selected + Shopify complementary keeps your selected products first, then adds the Shopify ones.
  - The collection is used in Collection mode. In the two Shopify modes, only your selected products and Shopify's suggestions are shown; if none remain, the group hides.
- **Products:** choose up to 12. The current product is excluded.
- **Collection**
- **Position on product page:** Below the buy buttons, Full width below product, Custom block position.
- **Cards visible on desktop:** 3 columns or 4 columns. Use 3 beside the photos and 4 for full width.
- **Photo shape:** Square, Portrait, Landscape.
- **Option spacing:** Compact, Comfortable.

Only the first Complete the kit block that matches the product is shown. A block that does not match is not shown on the storefront. In the theme editor it shows the note "Not shown on this product" while it is selected. A Text note block limited to selected collections is also hidden on the storefront and shows a note in its place in the theme editor.

Rules the theme always applies: sold-out products and products excluded in Theme settings > Product recommendations are skipped, duplicates are removed, and the list is capped at 12. On mobile, customers swipe one card at a time. Option values on these cards are shown as buttons, and colors as a swatch with the color name. The cards do not use dropdowns.

### Related products section

The **Related products** section sits below Product information. It loads Shopify's related recommendations. Settings: **Heading**, **Maximum products** (2 to 10, default 6), **Desktop columns** (2 to 4). If Shopify returns nothing, the section hides itself and the theme does not fill it from other collections.

### Excluding products from recommendations

In Theme settings > Product recommendations:

- **Hide jersey customizer products** (on by default). Keeps products that use the jersey template or have the tag `custom-jersey` out of recommendations.
- **Collection to exclude.** Products in this collection never appear in recommendations.

Also, any product with the tag `exclude-recommendations` is always excluded. These rules apply to Complete the kit, Related products and cart recommendations.

### Cart recommendations

Theme settings > Cart recommendations has its own settings (**Show cart recommendations**, **Heading**, **Source**, **Products**, **Collection**, **Desktop layout**, **Mobile layout**, **Product photo size**, **Option spacing**). The **Source** options are the same as in Complete the kit. The recommendation cards show option values as buttons, and colors as a swatch with the color name.

## 9. Gift card product and recipient form

### Create the product

1. In Shopify admin, add a product of type gift card (Products > Add product, then turn on **This is a gift card**), and set the denominations as variants.
2. Under Theme template, choose **product.gift-card**.

### Template

`templates/product.gift-card.json` holds: Vendor, Product heading, Price, Variant picker, Quantity selector, Buy buttons, Description, a Collapsible information block called **Digital delivery**, then the Related products section.

### Recipient form

In the Buy buttons block, **Show gift card recipient form** (on by default) adds a checkbox **Send this gift card to someone**. When ticked, the form shows:

- Recipient email
- Recipient name
- Message (up to 200 characters)
- Send on (optional date; leave empty to send now)

Email and date errors show inline. When the recipient form is on, accelerated checkout buttons are not shown. The pickup disclosure and size guide are never shown for gift cards.

### Denomination card preview

In Product information, under **Layout** (in Featured product, under **Advanced**), turn on **Show denomination card design**. The card shows your store name, the words "Digital gift card" and the amount of the selected variant. It is added above the product gallery. When the product has no media, the card replaces the gallery. The preset template has this on. Turn it off to use product media only.

### Gift card page

`templates/gift_card.liquid` is the page the customer opens from the email. It shows the shop name, the current balance, the original amount when the balance differs, the expiry date and scheduled send date when set, the code (with a **Copy code** button), a QR code, a **Print gift card** button, a link back to the store and an Add to Apple Wallet link when one exists. Statuses for disabled and expired cards are shown. The page does not use the store header or footer.

## 10. Filters (Search & Discovery)

Filters on collection and search pages come from Shopify Search & Discovery.

### Set up

1. Open **Search & Discovery** > **Filters**.
2. Click **Add filter** and pick from: Availability, Price, Product type, Vendor, Tag, product options such as Color and Size, and product metafields that you have enabled as filters.
3. Reorder them and save. They appear on collection and search pages straight away.

### What the theme shows

On the **Collection page** section:

- **Show filters** (on by default) turns filters on or off.
- **Filter layout:** Sidebar or Drawer.
- Types handled: list and boolean (checkboxes with counts, values with no matches are disabled) and price range (From and To fields).
- A filter named Color, Colour, Renk, Couleur, Farbe or Colore (or with a color parameter), or any value with a swatch, shows a color chip next to the label.
- Active filters show as removable chips and a count on the filter title. The Availability filter and any filter with active values open by default.
- **Show kit type chips** (`show_type_chips`, on by default, shown when Show filters is on) adds a row of quick filter chips above the product grid, one per product type, plus an **All** chip. It is built from the **Product type** storefront filter, so add Product type under Search & Discovery > Filters first. The row is shown only when the collection has more than one product type.
- **Show sorting** controls the sort menu. **Products per page** (8 to 48) and **Desktop columns** control the grid.

On the **Search results** section: **Show search filters** (on by default). Filters open in the same drawer as on collection pages: a **Filter** button above the results opens it, with the same list, boolean and price range types. Active filters show as removable chips above the results. The sort menu is next to the button. Filters and sorting are shown once a search has results or an active filter.

Tip: create swatches for Color option values in Shopify so filter chips show the right color.

## Quick checklist

- Each color variant has its own image.
- Color option values have swatch colors or use a name from the built-in list.
- `custom.sibling_products` is a list of products, set on every product of the group (when you sell colors as separate products).
- Unit price measurement set on variants that need it.
- Local pickup enabled on locations and on the Buy buttons block.
- Shop Pay Installments enabled in Shopify, if you want the payment terms banner.
- Complementary products configured in Search & Discovery, and a Complete the kit group set to Shopify complementary products.
- Gift card product uses the `product.gift-card` template.
- Filters configured in Search & Discovery.
