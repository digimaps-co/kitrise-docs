---
title: Colors and typography
---

# Colors and typography

Kitrise by digimaps.co. Unless a section is named, the settings below are in the theme editor under **Theme settings**. Labels match `config/settings_schema.json` and `locales/en.default.schema.json`.

## Colors

Theme settings > **Colors**

| Setting | Default | Notes |
| --- | --- | --- |
| Text | #000000 | Main text color. |
| Background | #fafaf9 | Page background. |
| Secondary background | #f3f3f3 | Used for alternate surfaces. |
| Secondary background text | #000000 | Text on the secondary background. |
| Accent | #121212 | Accent surfaces and solid elements. |
| Highlight | #1f7c75 | Used for sale badges. Keep contrast with white at 4.5:1 or better. |
| Highlight text | #ffffff | Text on highlight backgrounds, such as sale badges. |
| Accent text | #ffffff | Text and icons on the accent color and on solid buttons. |

These values are written as CSS variables by `snippets/css-variables.liquid` and used across the theme.

### Sale badge colors

Theme settings > **Product cards**

- **Sale badge background**: leave empty to use Highlight.
- **Sale badge text**: leave empty and the theme picks white or black, whichever has the higher contrast against the badge background.
- **Sale badge border**: leave empty to use Highlight.

### Product media colors

Theme settings > **Product media and cards**

- **Product media background**: a select with Gray (default), White, Ivory and Custom color.
- **Custom product media color** (default #f4f4f4): used when the background is set to the custom option.
- **Custom background text** (default #000000): the text color for the custom background. With any other background, the Text color is used.

## Section palettes

Most sections have a **Color palette** select (setting id `palette`). A few sections label it **Color scheme** or **Palette**. In most sections it adds a `fx-palette--<value>` class, and the section then uses that palette's background, text, muted text and line colors. A few sections, such as Hero and Countdown, apply the value through their own section class instead.

Values:

- **Light**: white background, near-black text.
- **Soft**: pale gray-green background, near-black text.
- **Dark**: near-black background, light text.
- **Accent**: uses the Accent color as background and Accent text as text color.
- **Brand colors**: uses the Background and Text colors from Theme settings > Colors. In most sections the setting info says: "Choose Brand colors to use the background and text colors from Theme settings > Colors."

Not every section offers every value. For example, Hotspots offers only Brand, Light and Soft, and most other sections add Dark and Accent. Some sections name the options Brand, White or Soft neutral. The editor shows only the options a section supports.

Each section lists its own palette options in its settings.

## Secondary text contrast

Secondary (muted) text is adjusted so it keeps at least 4.5:1 contrast against the Background color, for any Text and Background colors the merchant picks in Theme settings > Colors.

How it works, from `assets/critical.css`:

- The rule is in CSS, after the inline theme variables.
- It computes the WCAG luminance of the text color and the background color.
- It moves the text color toward the background by the largest share that still passes, capped at one half.
- The result replaces `--fx-brand-muted` and `--fx-color-muted`.
- It is wrapped in `@supports` for relative color syntax and `sign()`. Browsers without that support keep the base muted value, which is the text color at 62% opacity.

The fixed palettes (Light, Soft, Dark) use fixed muted colors. The Accent palette uses the Accent text color for muted text.

## Light and dark mode

Theme settings > **Color mode**

| Setting | Default | Notes |
| --- | --- | --- |
| Enable light and dark mode | On | Turns the feature on. When off, no toggle, script or dark stylesheet is loaded. |
| Default appearance | Light | Options: Light, Dark, Use device setting. |
| Dark background | #141817 | |
| Dark surface | #202622 | |
| Dark surface text | #F4F6F0 | |
| Dark text | #F4F6F0 | |
| Dark accent | #F18B7B | |
| Dark accent text | #171918 | |

Behavior:

- A toggle button lets the visitor switch between light and dark. Its label is "Dark mode" and its action text reads "Switch to dark mode" or the light equivalent.
- The choice is saved in the browser (`localStorage`) per theme. If storage is blocked, the page still works.
- A small inline script sets the mode before the page paints, to avoid a flash. With "Use device setting", it follows `prefers-color-scheme`.
- In dark mode, Light, Brand and Soft palettes switch to the dark colors. Soft uses the dark surface. The Dark palette keeps its own colors. The Accent palette uses Dark accent as background and Dark accent text as text.
- The browser `theme-color` meta tag follows the current background.

## Typography

Theme settings > **Typography**

| Setting | Default | Notes |
| --- | --- | --- |
| Body font | Shopify font picker, Barlow Regular | Font picker for body text. |
| Body size | 16 | Base size in px. |
| Additional body text scaling | 100 | Percent scale on body text sizes. |
| Heading font | Shopify font picker, Barlow Condensed Bold | Font picker for headings. |
| Heading size | 100 | Percent scale on all heading sizes. |
| Heading case (`heading_case`) | Uppercase | **Uppercase** or **As typed**. Uppercase sets theme headings in capitals. As typed shows them as you wrote them. |

Notes:

- Both pickers load the Shopify-hosted font with `font_face` and `font-display: swap`. Regular, bold, italic and bold italic faces are generated for each.
- Heading sizes are fluid (`clamp()`), five steps from extra small to extra large, all multiplied by the Heading size scale.
- Letter spacing and line height for headings and body are set in `snippets/css-variables.liquid`.

## Corner radius

Theme settings > **Shapes**

Buttons, inputs, cards, media and badges take their corner radius from these settings. Sections follow them, so a change here updates the whole store.

| Setting | Range | Default | Used for |
| --- | --- | --- | --- |
| Global corner radius (`corner_radius`) | 0 to 24 px | 8 | The single radius used when **Apply global radius** is on. |
| Apply global radius (`use_global_corner_radius`) | On or off | Off | When on, the global radius replaces the five radius settings below. |
| Button corner radius (`button_radius`) | 0 to 24 px | 2 | Buttons. |
| Button border thickness (`button_border_thickness`) | 0 to 4 px | 1 | Button borders. Not affected by Apply global radius. |
| Input corner radius (`input_radius`) | 0 to 24 px | 2 | Form fields. |
| Card corner radius (`card_radius`) | 0 to 24 px | 2 | Cards. |
| Media corner radius (`media_radius`) | 0 to 24 px | 2 | Images and other media. |
| Badge corner radius (`badge_radius`) | 0 to 40 px | 2 | Badges. |

A radius of 0 gives square corners.

Some sections have their own radius setting that takes precedence over the theme setting when you turn the theme link off:

- **Jersey customizer** and **Image comparison**: **Follow theme media radius** (`use_global_radius`, on by default) uses **Media corner radius**. Turn it off to show **Corner radius** (Jersey customizer, 0 to 24 px, default 2) or, under Show advanced settings, **Corner rounding** (Image comparison, 0 to 40 px, default 2).
- **Product information** and **Featured product**: **Use global product media radius** (`use_global_media_radius`, on by default) uses **Media corner radius** for the gallery. Turn it off to show **Image corner radius** (`media_radius`, 0 to 32 px, default 16).

## Jersey print fonts

Theme settings > **Jersey kit** has two font pickers for the printed name and number on the jersey preview and on the printed preview in the cart:

- **Athletic print font** (default Anton regular)
- **Classic print font** (default Libre Baskerville regular)

The **Print style** select in the **Jersey customizer** section (Athletic, Clean or Classic, default Athletic) picks which one is used. Each is loaded with `font_face` and swap display for the whole theme. The Jersey customizer section also has color settings **Preview background** (default #eeeee8) and **Preview text** (default #171918) for the preview canvas, plus its own **Color palette** select.
