---
title: Jersey Studio
---

# Jersey Studio

Jersey Studio lets a shopper pick a jersey, add a name, number or player, choose a print color and see a live preview before adding to the cart. It is the **Jersey customizer** section of Kitrise by digimaps.co. The theme ships with the `product.jersey` template and a `page.jersey-studio` template that both use it.

## What you need before you start

- One Shopify product per jersey model and category (Men, Women, Kids).
- On each product, a **Personalization** option with four values: `Plain`, `Name only`, `Name + number`, `Player`. Printing is charged through the variant price of these values.
- A **Size** option (the theme also reads a `Beden` option as size).
- Front images for each model. Back images are optional but needed for the back preview.

## 1. Assign the template

1. In Shopify admin, open the product.
2. Set the theme template to **jersey** (`templates/product.jersey.json`).
3. Optional: add the tag `custom-jersey` to the product. When **Hide jersey customizer products** is on (Theme settings > Product recommendations; default on), products on the `jersey` template and products with this tag are left out of shopping recommendations. The tag also hides a legacy "no patch" option row in the cart.

Products on the `jersey` template are also detected by product cards. Where cards show quick view, these products show a **Customize** link instead, which opens the product page.

The template contains these sections, in order: Jersey customizer, FAQ ("Your jersey, explained."), a products section ("Find your team colors.") and related products.

## 2. Set up the variants

The section matches option names and values by text, ignoring case. The defaults are:

| Section setting | Default |
| --- | --- |
| Product option name | Personalization |
| Plain option value | Plain |
| Name only option value | Name only |
| Name and number option value | Name + number |
| Player option value | Player |

If your product uses other words, change these five settings to match exactly.

How it works:

- Each print mode resolves to the variant whose Personalization value matches. Prices come from that variant and stay the same in the cart.
- The price difference between `Plain` and the chosen mode is shown beside each print option (when **Show price beside each printing option** is on). A zero difference shows "Included".
- **Printing pricing** has two choices. *Paid printing, uses product variants* (default) needs a variant for each mode. A missing variant means the mode shows as unavailable and cannot be ordered. *Printing included at no extra charge* always uses the Plain variant price for every mode.
- If a product has no Personalization option and pricing is set to paid printing, only the plain jersey can be ordered. In the theme editor a setup note explains this.
- Sold out variants disable the matching print option.
- A legacy option named `Patch`, `Badge`, `Arma` or `Rozet` is supported. Only the variants whose value is "No patch", "None" and similar are used.
- Other options (for example a second color option) appear under the size step.

Sizes come from the real product variants. Sizes and other option values are shown as buttons, and colors as a swatch with the color name. The steps are identified by their titles (for example "Find your fit" and "Make it yours"), not by numbers. Set **Size guide page** (a page opened in a dialog) or **Size guide link** to show a "Size guide" link in the size step.

## 3. Add jersey model blocks

Add one **Jersey model** block per product (up to 15). Each block has:

| Setting | Purpose |
| --- | --- |
| Product | The real product. Size and color options come from its variants. |
| Matching design key | Use the same key (for example `velocity`) on the Men, Women and Kids versions of one design. The design stays selected when the shopper switches category. |
| Category | Men, Women, Kids or Adults (men and women). |
| Short name | Label on the model card. Falls back to the product title. |
| Front image | Preview image. Falls back to the product featured image. |
| Back image | The real back view. Printing is shown only on this image. |
| Model swatch | Color dot on the card. Also used for the contrast warning. |
| Suggested print color | Pre-selected when it matches one of the Print color blocks, until the shopper picks a color. |
| Name: distance from top, Number: distance from top, Name size, Number size | Print placement in percent of the image. |

With **Show advanced settings** on the block, **Print: distance from left** and **Print area width** appear.

A block without a product is not shown in the builder. If no block has a product, the section shows an empty state; in the editor it says "Add a product to a Jersey model block to enable the builder."

The shopper chooses a category first (Men, Women, Kids), then a model in that category. Adult blocks show for Men and Women.

## 4. Add print color blocks

Add **Print color** blocks (up to 8) with a **Color name** and **Color**. The first one is selected when the model's suggested print color does not match a block. The color name is saved on the order. If there are no color blocks, a single White option is used.

Turn on **Allow any print color** (under Show advanced settings on the section) to add a free color picker. Use it only if your print service supports any color.

Print colors are disabled while the shopper has "No personalization" selected.

## 5. Add player blocks

Add **Player** blocks (up to 20) with **Player name**, **Shirt number** and **Show for** (All categories, Men, Women, Kids). The name must fit within **Maximum name length** and the number must be digits within **Maximum number length**. Players that break these rules, and players set to another category, are left out of the list. The shopper sees them as "name · number" in a Player menu and the selected name and number print on the back.

## Print modes in the storefront

The "Make it yours" step offers up to four modes. Each can be hidden with the checkboxes **Use name only**, **Use name and number**, **Use player selection**. "No personalization" is always available.

| Mode | Fields shown | Variant used |
| --- | --- | --- |
| No personalization | None | Plain |
| Name only | Name (required) | Name only |
| Name and number | Name and Number (both required) | Name + number |
| Choose a player | Player menu (required) | Player |

Limits and formatting (under **Show advanced settings** on the section):

- **Maximum name length**: 6 to 24, default 14.
- **Maximum number length**: 1 to 3 digits, default 2. Only digits are accepted.
- **Name lettering**: Uppercase (default) or As entered.

Name and number placeholders are set in the Content group with **Name placeholder** (default "YOUR NAME") and **Number placeholder** (default "07").

The theme editor remembers the shopper-side preview state while you edit and selects the matching model or player when you click its block.

## Line item properties

On add to cart the theme sends these properties with the variant:

| Property | When |
| --- | --- |
| Category | Always (Men, Women or Kids). |
| Player | Player mode. |
| Name | When a name is printed. |
| Number | When a number is printed. |
| Print color | When a name or number is printed. Custom colors read "Custom color: #HEX". |
| `_Jersey name font`, `_Jersey name size`, `_Jersey name position` | When a name is printed. Font holds the print style. |
| `_Jersey number font`, `_Jersey number size`, `_Jersey number position` | When a number is printed. |

In the cart, a line of a jersey product shows a one-line summary under the product title: the product type, the size, then the printed name and number, for example "Home kit · M · KAYA 10". The size is read from the Size option (or `Beden`). Other options and details, such as the personalization type and print color, stay listed below it.

Properties starting with an underscore are hidden from the cart display. The label text for the visible properties comes from the theme locale strings (`property_audience`, `property_player`, `property_name`, `property_number`, `property_color`). If the theme cart script is not available, the same properties are written as hidden form fields and the form submits normally.

## Print style and fonts

**Print style** has three choices: Athletic (default), Clean and Classic.

- **Athletic print font** (default Anton) is used by Athletic.
- **Classic print font** (default Libre Baskerville) is used by Classic.
- Clean uses the theme body font.

Both are font pickers. Fine tune placement with **Name size adjustment** and **Number size adjustment** (50 to 160 percent) and **Name vertical adjustment** and **Number vertical adjustment** (minus 10 to 10 percent; negative moves up). Model blocks set the base size and position.

## Contrast warning

When a print mode is selected, the theme compares the model swatch color to the print color. If the contrast ratio is below 1.5 it shows: "This print color may be hard to read on this jersey. Choose a contrasting color." This is a hint only and does not block the order. Set a swatch color that matches the real jersey so the check is accurate.

## Preview and galleries

- **Live preview** shows front and back views. The Back button is disabled for models without a back image, and a note explains that personalization still appears in the order summary.
- **Allow enlarged preview** adds an enlarge button with a dialog.
- On a product page, the product media gallery sits below the builder and follows the selected model. Each model block with a product that has media gets its own gallery, and only the selected one is shown. 3D models on the product are supported.
- The form always shows a quantity field. On a product page the section also shows accelerated checkout (**Show accelerated checkout**, shown for plain jerseys only) and local pickup (**Show local pickup availability**).
- A model product description is shown under the price for the selected model.

## Section settings reference

**Layout**: Layout (Preview on the left, Preview on the right, Stacked), Section width (960 to 1800 px, default 1440).

**Content**: Subheading, Heading, Use as the page heading (use only for the main section on a page; product pages use the product title), Description, Name placeholder, Number placeholder.

**Printing and pricing**: Printing pricing, Show price beside each printing option, Show jersey and printing breakdown, Use name only, Use name and number, Use player selection, the five option name and value fields, Price note, Size guide page, Size guide link.

**Appearance**: Color palette (Light, Soft, Dark, Accent, Brand colors), Preview background, Preview text, Corner radius (0 to 24 px), Print style.

**Print typography and placement**: Athletic print font, Classic print font, Name and Number size and vertical adjustments, Allow enlarged preview, Show accelerated checkout, Show local pickup availability, Top spacing, Bottom spacing.

**Mobile**: Preview height on mobile (200 to 520 px), Top spacing on mobile, Bottom spacing on mobile.

**Advanced**: Show advanced settings, Maximum name length, Maximum number length, Name lettering, Allow any print color.

The section also accepts app blocks and a **Custom Liquid** block, rendered below the form.

## Setup checklist

1. Create products with `Size` and `Personalization` options and set prices per variant.
2. Assign the `jersey` template to each product.
3. In the template, add a Jersey model block for each product and set its Category, Matching design key, images and swatch.
4. Add Print color blocks and, if needed, Player blocks.
5. Check the option names and values in Printing and pricing against your products.
6. Test every mode on desktop and mobile, then add a test order and confirm the properties in the order.

## Limits

- Name and number are printed from the text the shopper enters. The preview is a guide, not a production proof; the preview note tells shoppers that final print placement and colors may vary slightly.
- The preview needs JavaScript. Without it, shoppers can order the plain jersey only.
- For team orders with many names, direct shoppers to your contact page. The default FAQ says so.
