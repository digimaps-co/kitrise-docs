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
| Back image | The real back view. Printing is shown only on this image. When it is empty, the theme takes the back from the product's own media, following **Back image of the shirt** in Theme settings > **Jersey kit** (see "Jersey stage on product cards" below). |
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

## Squad order

Use a squad order when a shopper buys shirts for a whole team. The section settings are in the **Squad order** group of the **Jersey customizer** section:

| Setting | Default | Purpose |
| --- | --- | --- |
| Allow squad orders (`enable_squad_order`) | On | Shows an **Order type** switch with **One shirt** and **Squad order**. |
| Maximum players per squad order (`squad_max_rows`) | 25 | Number of roster rows, 2 to 30. Shown when squad orders are on. |

The switch needs JavaScript. With **Squad order** selected:

- The **Squad roster** step opens. The size, print mode and player steps of the single shirt flow are replaced by the roster. Model, audience and print color apply to the whole squad.
- The roster starts with three empty rows (fewer if the maximum is lower). Each row has a name, a number and a size. **Add player** adds a row until the maximum is reached. **Remove** deletes a row. Enter in the name field moves to the number, and Enter in the number moves to the next row or adds one.
- The number accepts digits up to **Maximum number length**. The name follows **Maximum name length** and **Name lettering**.
- The print mode of a row follows what is filled in: a name and a number use the **Name + number** variant, a name alone uses the **Name only** variant, and a row with only a size uses the **Plain** variant. A number without a name is not accepted. Rows for a print mode that is switched off in the section settings, or that has no matching variant, show an error.
- If the product has a Size option, every filled row needs a size. A size that is sold out with the chosen print shows an error on that row. Rows that are completely empty are ignored.
- Each row is one shirt, quantity 1. The total beside the add button is the sum of the variant prices of the filled rows.

### Pasting a list

**Paste a list** opens a text box. Enter one player per line in the order name, number, size, separated by a tab, comma or semicolon. Number and size are optional. **Add to roster** fills the empty rows first and then adds rows up to the maximum. A line is left in the text box, and a message lists the reason, when:

- its size is not one of the product sizes (unknown size). The theme compares sizes ignoring case;
- the roster is full;
- it has no name and no number.

If the product has no Size option, a size in the pasted line is ignored.

### Adding to the cart

The squad button reads **Add your squad to bag** while the roster is empty, and "Add 12 shirts to bag" (or "Add 1 shirt to bag") once rows are filled. It sends every filled row in one request. If any row has an error, nothing is added and the rows that need attention are marked. After a successful add the roster is cleared.

In the cart, the lines of one squad are listed together under a **Squad order** heading with the number of shirts, for example "12 shirts". The theme groups lines that share the same `_Jersey squad` value.

## Line item properties

On add to cart the theme sends these properties with the variant:

| Property | When |
| --- | --- |
| Category | Always (Men, Women or Kids). |
| Player | Player mode. |
| Name | When a name is printed. |
| Number | When a number is printed. |
| Print color | When a name or number is printed. Custom colors read "Custom color: #HEX". |
| `_Jersey name` | When a name is printed. The cart reads the printed name from this key. |
| `_Jersey number` | When a number is printed. The cart reads the printed number from this key. |
| `_Jersey name font`, `_Jersey name size`, `_Jersey name position` | When a name is printed. Font holds the print style. |
| `_Jersey number font`, `_Jersey number size`, `_Jersey number position` | When a number is printed. |
| `_Jersey print color` | When a name or number is printed. The print color as a hex value, for example `#ffffff`. The cart uses it to draw the printed preview. |
| `_Jersey print left`, `_Jersey print width` | When a name or number is printed. Horizontal position and width of the print area, in percent of the image. |
| `_Jersey squad` | Squad orders only. One batch id shared by every line added in the same squad order. |
| `_Jersey squad row` | Squad orders only. The position of the player in the order, starting at 1 and counting only the filled rows. |

In the cart, a line of a jersey product shows a one-line summary under the product title: the size, then the printed name and number, for example "M · KAYA 10". The product type is shown above the title as the kit tag. The size is read from the Size option (or `Beden`). Other options and details, such as the personalization type and print color, stay listed below it.

Squad lines carry the same properties as single shirts, except `Player`, plus the two squad keys. Properties starting with an underscore are hidden from the cart display. The label text for the visible properties comes from the theme locale strings (`property_audience`, `property_player`, `property_name`, `property_number`, `property_color`). If the theme cart script is not available, the same properties are written as hidden form fields and the form submits normally.

## Print style and fonts

**Print style** has three choices: Athletic (default), Clean and Classic.

- **Athletic print font** (default Anton) is used by Athletic.
- **Classic print font** (default Libre Baskerville) is used by Classic.
- Clean uses the theme body font.

Both fonts are font pickers in Theme settings > **Jersey kit**, so the customizer and the cart preview use the same fonts. Fine tune placement with **Name size adjustment** and **Number size adjustment** (50 to 160 percent) and **Name vertical adjustment** and **Number vertical adjustment** (minus 10 to 10 percent; negative moves up). Model blocks set the base size and position.

## Contrast warning

When a print mode is selected, the theme compares the model swatch color to the print color. If the contrast ratio is below 1.5 it shows: "This print color may be hard to read on this jersey. Choose a contrasting color." This is a hint only and does not block the order. Set a swatch color that matches the real jersey so the check is accurate.

## Preview and galleries

- **Live preview** shows front and back views. The Back button is disabled for models without a back image, and a note explains that personalization still appears in the order summary.
- **Allow enlarged preview** adds an enlarge button with a dialog.
- On a product page, the product media gallery sits below the builder and follows the selected model. Each model block with a product that has media gets its own gallery, and only the selected one is shown. 3D models on the product are supported.
- The form always shows a quantity field. On a product page the section also shows accelerated checkout (**Show accelerated checkout**, shown for plain jerseys only) and local pickup (**Show local pickup availability**).
- A model product description is shown under the price for the selected model.

## Jersey stage on product cards

Products that use the `jersey` product template can show a **Front** / **Back** switch on their product cards. The switch is part of the theme's product card.

The back image comes from the product's own media. Choose the rule in Theme settings > **Jersey kit** > **Back image of the shirt** (`jersey_back_source`):

| Option | Back image |
| --- | --- |
| No back image | Cards show no switch. |
| Second product image | The second image in the product media list. |
| Last product image (default) | The last image in the product media list. |

To make it work:

1. In Shopify admin, open the product and drag the front image to the first place in the media list. The first image is the featured image and is always the front.
2. Put the back image second, or last, to match the option you chose. With only one extra image, both options pick the same image.
3. The back must be an image (not a video or 3D model) and must not be the same picture as the front. If the product has only one media item, or the back is the same as the shown front image, the card shows no switch.

Notes:

- The product must use the `jersey` template. Other products keep their normal hover image.
- On cards the back is compared only with the product's featured (first) image. The comparison with a color variant's own front image applies only to the cart line image.
- In the Jersey customizer, a model with an empty **Back image** uses the same rule.

## Printed preview in the cart

In the cart, a line of a jersey product shows the shirt image. When the line has a printed name or number, the image shows the back of the shirt with the shopper's name and number drawn on it, in the print color, style, size and position the shopper chose.

The preview is drawn from the hidden line item properties saved when the shirt was added (see "Line item properties"). It needs the print text, `_Jersey print color` and a back image from **Back image of the shirt**. Lines added before these properties existed, lines without a name or number, and products without a back image show the front image instead.

Kit lines in the cart also show the product type as a kit tag above the title (see "Kit tag" in Products, variants and metafields).

## Section settings reference

**Layout**: Layout (Preview on the left, Preview on the right, Stacked), Section width (960 to 1800 px, default 1440).

**Content**: Subheading, Heading, Use as the page heading (use only for the main section on a page; product pages use the product title), Description, Name placeholder, Number placeholder.

**Printing and pricing**: Printing pricing, Show price beside each printing option, Show jersey and printing breakdown, Use name only, Use name and number, Use player selection, the five option name and value fields, Price note, Size guide page, Size guide link.

**Appearance**: Color palette (Light, Soft, Dark, Accent, Brand colors), Preview background, Preview text, Follow theme media radius (on by default; uses **Media corner radius** from Theme settings > **Shapes**), Corner radius (0 to 24 px, default 2, shown when Follow theme media radius is off), Print style.

**Print typography and placement**: Name and Number size and vertical adjustments, Allow enlarged preview, Show accelerated checkout, Show local pickup availability, Top spacing, Bottom spacing.

**Mobile**: Preview height on mobile (200 to 520 px), Top spacing on mobile, Bottom spacing on mobile.

**Squad order**: Allow squad orders, Maximum players per squad order.

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
- A squad order holds up to 30 players. For larger teams, direct shoppers to your contact page. The default FAQ says to contact you for team orders.
