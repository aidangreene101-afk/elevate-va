# Elevate VA

A single-file marketing site + client portal for a premium virtual-assistant service.
Everything is in `index.html` — no build step, no server, no dependencies. Open it in a
browser or drop it on any static host.

## What already works (done for you)

- **Responsive landing page** — hero, process, services, pricing, testimonials, CTA.
- **Lead capture form** with a safe fallback: if Formspree isn't configured yet, the
  form opens the visitor's email client pre-filled to your address, so no lead is lost.
- **Pricing buttons** route to Stripe when configured, and otherwise open the
  consultation form instead of a dead link.
- **Working client portal** — tasks submitted on the "Submit a task" page persist in the
  browser (localStorage), show up in the dashboard, survive reloads, and can be cleared.
- **Honest urgency** — the countdown anchors to each visitor's first visit and does not
  reset on reload; the "founding spots" number is a single config value.
- **SEO / social** — title, description, Open Graph + Twitter tags, and an inline favicon.
- **Privacy Policy page** wired into the footer.

## Go live: the 4 things only you can do

All settings live in one `CONFIG` object at the top of the `<script>` block in
`index.html`. A value counts as "not set up" while it still contains the word `REPLACE`.

1. **Contact email** — set `CONFIG.email` to your real address.
2. **Lead form (Formspree)** — sign up free at https://formspree.io, create a form, and
   put its ID (e.g. `xrgkabcd`) in `CONFIG.formspreeId`. Until then the form uses the
   email fallback.
3. **Booking link** — set `CONFIG.calLink` to your Cal.com or Calendly URL.
4. **Payments (Stripe)** — create Payment Links at
   https://dashboard.stripe.com/payment-links for each plan (monthly + annual) and paste
   them into `CONFIG.stripe`. Make sure the prices there match the ones shown on the page.

Optional: set `CONFIG.foundingSpots` to your real remaining count (or `null` to hide the
founding bar), and `CONFIG.foundingDeadline` to a fixed end date if you want a shared
deadline instead of a per-visitor 7-day window.

## Before you publish — please read

Three things on the page are currently **placeholder content that is not legal to
publish as-is** (they're marked with `⚠️` comments in `index.html`):

- **Testimonials** — the four quotes and names are invented. Publishing fake testimonials
  violates the FTC's fake-reviews rule (fines up to ~$51,000 per violation) and similar
  laws elsewhere. Replace them with real, permissioned testimonials or delete the section.
- **Stat numbers** — "500+ hours saved", "98% satisfaction", "2h response" are invented.
  Use real figures or remove them.
- **Hero social proof** — "Joined by 200+ founders this month" and the avatar row are
  invented. Same rule applies.

The dashboard persona ("Sarah" / "Maya Chen" / completed-task counts) is a demo. It's fine
as an illustrative preview, but it is not a real per-user account system — that would need
authentication and a backend, which is beyond a static site.

## Hosting

Any static host works. Easiest free options: push this repo to GitHub and enable **GitHub
Pages**, or drag the folder onto **Netlify** or **Cloudflare Pages**. Point your domain at
the host and you're live.
