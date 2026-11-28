---
title: Kitrise support
---

# Kitrise support

Kitrise is built and supported by digimaps.co.

## Contact form

Send a support request with the form below. Replies are sent on business days, within 2 business days.

<form class="support-form" action="https://formsubmit.co/support@digimaps.co" method="POST" enctype="multipart/form-data">
  <input type="hidden" name="_subject" value="Kitrise support request">
  <input type="hidden" name="_template" value="table">
  <input type="hidden" name="_next" value="https://digimaps-co.github.io/kitrise-docs/support-sent.html">
  <input type="hidden" name="_autoresponse" value="Thanks for contacting Kitrise support. Your request has arrived and a reply will follow within 2 business days.">
  <input type="text" name="_honey" class="support-form__trap" tabindex="-1" autocomplete="off" aria-hidden="true">

  <label for="support-name">Name</label>
  <input id="support-name" name="name" type="text" autocomplete="name" required>

  <label for="support-email">Email</label>
  <input id="support-email" name="email" type="email" autocomplete="email" required>

  <label for="support-store">Store URL</label>
  <input id="support-store" name="store_url" type="text" inputmode="url" placeholder="your-store.myshopify.com" aria-describedby="support-store-hint">
  <small id="support-store-hint">The .myshopify.com address of the store that uses Kitrise.</small>

  <label for="support-version">Theme version</label>
  <input id="support-version" name="theme_version" type="text" placeholder="1.0.0" aria-describedby="support-version-hint">
  <small id="support-version-hint">Shown in the theme editor under Theme settings, Theme information.</small>

  <label for="support-message">Describe the issue</label>
  <textarea id="support-message" name="message" rows="8" required aria-describedby="support-message-hint"></textarea>
  <small id="support-message-hint">Include the page and the steps that lead to the issue.</small>

  <label for="support-file">Screenshot or screen recording (optional)</label>
  <input id="support-file" name="attachment" type="file" accept="image/png, image/jpeg, image/webp, video/mp4, application/pdf">

  <button type="submit">Send request</button>
</form>

<style>
  .support-form { display: grid; gap: 6px; max-width: 520px; margin: 16px 0 32px; }
  .support-form label { font-weight: 700; margin-top: 12px; }
  .support-form input[type="text"],
  .support-form input[type="email"],
  .support-form textarea { width: 100%; box-sizing: border-box; padding: 10px 12px; font: inherit; color: #111; background: #fff; border: 1px solid #767676; border-radius: 4px; }
  .support-form input:focus-visible,
  .support-form textarea:focus-visible,
  .support-form button:focus-visible { outline: 3px solid #1a5fb4; outline-offset: 2px; }
  .support-form small { color: #555; }
  .support-form button { justify-self: start; margin-top: 16px; padding: 12px 20px; font: inherit; font-weight: 700; color: #fff; background: #111; border: 0; border-radius: 4px; cursor: pointer; }
  .support-form__trap { position: absolute; left: -9999px; width: 1px; height: 1px; opacity: 0; }
</style>

You can also email **support@digimaps.co**.

## What support covers

- Questions about theme settings, sections and blocks.
- Bugs in the theme code.
- Guidance on theme updates.

Support does not cover custom code changes, third-party apps or store setup outside the theme.

## Before you write

Most setup questions are answered in the [documentation](index.html).
