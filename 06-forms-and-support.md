---
title: Forms and support
---

# Forms and support

Kitrise by digimaps.co uses Shopify's built-in forms. Messages and signups go to your Shopify admin, not to a third-party service. This page covers the contact form, newsletter forms, blog comments, cart notes, and how to get help.

## Contact form

Add the **Contact form** section to any page in the theme editor. It shows an optional subheading, heading and text, then the form.

Fields that are always shown: name, email, message.

Settings you can change:

| Setting | What it does |
| --- | --- |
| Layout | Split or Reading width. |
| Subheading, Heading, Text | Text above the form. If the heading is empty, a default "Contact" heading is used. |
| Contact details | Rich text shown under the intro text. Use it for your real contact information and reply times. |
| Show phone field | Adds a phone field. |
| Show inquiry topic | Adds a topic dropdown. |
| Preselected topic | Topic chosen when the page loads. Only shown when the topic field is on. |
| Show optional order number | Adds an optional order number field. |
| Color palette, Heading size | Light, Soft, Dark, Accent or Brand colors, and Standard or Large heading. |
| Mobile top spacing, Mobile bottom spacing | Spacing on small screens. |
| Show advanced settings | Reveals Section width, Top spacing and Bottom spacing. |

### Topics and the preselected topic

The topic dropdown has four choices:

- Product and sizing
- An existing order
- A team or group order
- Something else

**Preselected topic** decides which one is selected by default. The default is "Product and sizing". The customer can still change it.

### Team and bulk order pages

The theme includes two page templates for this, `page.teamwear` and `page.orders`. Both use a Contact form section with **Preselected topic** set to "A team or group order", so a visitor who wants a bulk order arrives with the right topic selected. To build your own bulk order page, add a Contact form section to a page and set **Preselected topic** the same way. Use the **Text** and **Contact details** settings to ask for products, sizes and quantities.

### Support fields (for theme support only)

The section has a group called "Theme support fields": Ask for the store URL, Show a screenshot link field, and Theme name for support requests. Leave these empty and off on your customer-facing contact page. They are meant for a theme support form.

### Where messages go

Messages are sent through Shopify's contact form. They arrive at your store's sender email address, set in Shopify admin (Settings > Notifications). The form shows a success message after sending and an error message if a field is missing or invalid.

## Newsletter forms

All newsletter forms use Shopify's customer form and tag the new contact with `newsletter`. Subscribers appear in Shopify admin under Customers. The theme does not connect to an email marketing app by itself. Use Shopify Email or your own app to send campaigns to the tagged customers.

### Footer

In the **Footer** section:

- Show newsletter
- Newsletter heading
- Newsletter text
- Newsletter note (small text under the form, for example an unsubscribe notice)

### Section

Add the **Email signup** section to any page.

- Layout: Wide band or Split
- Subheading, Heading, Text
- Image and Mobile image (optional), shown in the Split layout only
- Consent and privacy text
- Color palette: Light, Soft, Dark, Accent or Brand colors
- Mobile spacing, and Advanced controls for width and desktop spacing

### Popup

The **Welcome popup** section is included in the footer group, so one popup covers the whole store. Only one Welcome popup can be added to a section group or template. Select it in the theme editor to preview it.

- Show on the online store: off by default. Turn it on to publish the popup.
- Open trigger: After delay, or After browsing interaction.
- Delay before opening: 0 to 30 seconds.
- Show again: Once per session, After 1 day, After 7 days or After 30 days.
- Show only on the home page.
- Hide for subscribed customers: on by default.
- Version: change it when you want returning visitors to see a new message.
- Content type: **Newsletter signup** shows an email form. **Message and link** shows a button that goes to the **Button link** you set.
- Subheading, Heading, Description, Button label, Dismiss button label, Signup information (newsletter mode).
- Desktop image, Mobile image, Show image on mobile, Image position, Image width, Text alignment, Color palette, Maximum width, Corner radius, Desktop and Mobile heading size, Background dimming.

Popup signups carry the `newsletter` tag, like all other signups.

### Password page

The **Password page** section shows an optional email signup while your store is locked.

- Show email signup
- Email signup heading
- Email signup text

Visitors can also open "Enter with password" and type the storefront password.

## Blog comments

The article page shows comments and a comment form only when comments are enabled for that blog in Shopify admin (Content > Blog posts > Manage blogs). Turn them off there and the whole comments block disappears.

- The form asks for name, email and comment.
- If you chose moderation for the blog, a note tells readers that comments are reviewed first, and the success message says the comment will appear after approval.
- Existing comments are listed with author and date, ten per page.

The theme has no setting for comments of its own. Comments are controlled in Shopify admin.

## Cart notes

Customers can leave a note for your team with their order.

- **Theme settings > Cart > Show cart note** turns the note on or off in the cart drawer.
- In the **Cart** section on the cart page: **Show order note** turns the note on or off on the cart page, and **Open order note by default** opens the panel there.
- The note field is a collapsed "Add an order note" panel with a 5,000 character limit. The note is saved with the cart as the customer types and is stored on the order.

## Support

**How to get help**

Email admin@digimaps.co. Include:

- Your store URL
- The theme version (Theme settings shows `1.0.0` for the first release)
- What you expected and what happened
- A screenshot or a screen recording link
- Collaborator access, if support asks for it

**What support covers**

- Questions about how theme settings and sections work
- Bugs in the theme code
- Help with settings that do not behave as described in this documentation

**What support does not cover**

- Custom code changes and new features
- Issues caused by third-party apps
- Content, product data and Shopify account setup

**Theme updates**

New versions are published through the Shopify Theme Store. When an update is available, Shopify shows it in **Online Store > Themes**. Updates are added as a new copy of the theme, so your published theme stays untouched until you choose to switch. Duplicate your theme before an update and re-check any custom code you added.

## FAQ

**Where do contact form messages go?**
To your store's sender email address, set in Shopify admin under Settings > Notifications. Check your spam folder if you see none.

**Can I use the contact form for bulk orders?**
Yes. Set **Preselected topic** to "A team or group order", and use the Text setting to ask for products, sizes and quantities. The `page.teamwear` and `page.orders` templates already do this.

**How do I see who subscribed?**
In Shopify admin, open Customers and filter by the `newsletter` tag.

**Why is my popup not showing?**
Check that **Show on the online store** is on, that **Show only on the home page** is off if you expect it on other pages, that the visitor has not already seen or closed it within your **Show again** period, and that **Hide for subscribed customers** is not hiding it for a logged-in subscriber. Changing **Version** shows it again to everyone.

**Why is there no comment form on my blog post?**
Comments are off for that blog. Enable them in Shopify admin under the blog's settings.
