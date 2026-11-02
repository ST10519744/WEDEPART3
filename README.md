# Whisker & Wag Pet Co. – Website Project

## Project Title
Whisker & Wag Pet Co. – Website Development (WEDE5020 PoE, Parts 1–3)

## Student Information
- **Name:** Lucas Mabula
- **Student number:** ST10519744
- **Module:** WEDE5020
- **Institution:** The Independent Institute of Education (IIE)
- **Year:** 2026

## Live Site and Repository
- **Live website:** https://YOURUSERNAME.github.io/whiskers_and_wag/
- **Repository:** https://github.com/YOURUSERNAME/whiskers_and_wag
- **Hosting:** Netify (free, served over HTTPS)

## Project Overview
Whisker & Wag Pet Co. is a fictional independent pet store founded in 2018 in Pretoria by two former veterinary nurses. It has branches in Hatfield and Centurion, sells food and accessories for dogs, cats and small animals, and runs an in-store dog grooming salon. The business had no website; customers relied on Facebook and phone calls. This project builds a five-page website that lets customers browse the range, check prices and availability, enquire online, and find both branches.

## Website Goals and Objectives
- Let customers browse products and grooming services with prices and availability.
- Reduce phone enquiries by answering cost and availability questions online.
- Make the business findable in local search (Pretoria, Hatfield, Centurion).
- Give customers a simple way to contact either branch.

## Key Features and Functionality
| Page | File | Main features |
|------|------|---------------|
| Home | `index.html` | Hero, why choose us, shop by pet, **gallery with lightbox**, testimonial, internal links |
| Services | `services.html` | **Dynamic list loaded from JavaScript, with search, filter and sort**; FAQ **accordion** |
| Enquire | `enquiries.html` | **Validated enquiry form**, AJAX submit, instant cost and availability quote |
| About us | `about.html` | Story, mission, vision, team |
| Contact | `contact.html` | Both branches, **Google Maps embed for each branch**, **validated contact form that compiles an email** |

Shared files: `css_assets/mystyles.css` (styles), `js_assets/script.js` (all JavaScript), `robots.txt`, `sitemap.xml`.

## Timeline and Milestones
- **Part 1:** Proposal, wireframes, sitemap and content plan.
- **Part 2:** Five-page HTML site with external CSS, Grid/Flexbox layout, pseudo-classes and responsive breakpoints.
- **Part 3:** JavaScript functionality, SEO, validated forms, deployment, and Part 2 feedback corrections.

## Sitemap
```
Home (index.html)
├── Services (services.html)
├── Enquire (enquiries.html)
├── About us (about.html)
└── Contact (contact.html)
```

## Part 3 Details

### JavaScript enhancements (`js_assets/script.js`)
- **Accordion** (Services FAQ): buttons toggle `aria-expanded` and show or hide each answer panel.
- **Lightbox gallery** (Home): clicking a photo opens it larger in an overlay with previous/next buttons, arrow-key support and an image counter; Escape or a click outside closes it and focus returns to the photo.
- **Maps** (Contact): a keyless Google Maps embed for each branch; visitors can zoom, pan and get directions inside it. Unlike the other features, this is an embed, not scripted.
- **Animation:** CSS transitions triggered by an `IntersectionObserver` fade cards in as they scroll into view; disabled for users who prefer reduced motion.
- **Advanced DOM manipulation:** the Services list, the Enquire dropdown and the quote are all built with `createElement` and `textContent` rather than hard-coded HTML.
- **Dynamic content and search:** the Services page renders from a `catalogue` array, with live search, a category filter and sorting by name or price.

### Forms and validation
- **`enquiries.html`:** name, email, South African phone number, product or service, quantity, preferred date, a reply-method radio group, a stock-alert checkbox, a required consent checkbox and the question. On valid input the form is sent with `fetch` (AJAX) to the URL in the form's `action` attribute (JSONPlaceholder test API) and the page shows the quote (price × quantity) and availability.
- **`contact.html`:** name, email, optional phone, message type and message. On valid input the data is compiled into an email addressed to `lucasponsho23@gmail.com` (set in the `CONTACT_RECIPIENT` constant) and the user sends it with a `mailto:` link, or with an "Open in Gmail" link if no email app is set up.
- **Validation rules:** required fields, email format, 10-digit phone number starting with 0, minimum and maximum lengths, quantity 1–20, and no past dates. Errors appear under each field and focus moves to the first invalid field.

### SEO
- **Keywords:** researched around what local pet owners search for, with a different set per page, each phrase appearing word-for-word in that page's visible text. Home: pet store in Pretoria, dog grooming in Pretoria, pet shop in Centurion, pet food in Hatfield. Services: dog grooming in Pretoria, pet supplies, cat food, grooming prices. Enquire: pet product enquiry, dog grooming price, product availability, cost estimate. About: independent pet store, former veterinary nurses, pet store in Hatfield, dog groomer. Contact: pet store in Hatfield, pet shop in Centurion, opening hours, contact us.
- **Titles and meta descriptions:** unique for every page.
- **Headings:** one `<h1>` per page, with `<h2>` and `<h3>` used for structure.
- **Images:** descriptive file names (for example `dog-grooming-services.jpg`), descriptive alt text, width and height attributes, and lazy loading.
- **URLs:** short, lowercase and descriptive.
- **Internal linking:** contextual links between pages inside body text.
- **Mobile-friendliness:** viewport meta tag and responsive breakpoints at 768px and 480px.
- **Structured data:** `PetStore` JSON-LD on the Contact page for local SEO.
- **`robots.txt`:** allows crawling and points to the sitemap; `/private/` is disallowed.
- **`sitemap.xml`:** lists all five pages.
- **Page speed:** lazy-loaded images, one shared CSS and one shared JS file, scripts loaded with `defer`.
- **Security:** served over HTTPS by GitHub Pages; user input is written to the page with `textContent` (never `innerHTML`); no API keys or passwords in the code.
- **Off-page SEO (plan):** list the business on Google Business Profile for both branches, share the site on Facebook where the store already has about 4,800 followers, and ask local pet and veterinary businesses for backlinks.

### Deployment
Deployed on GitHub Pages: repository **Settings → Pages → Deploy from a branch → `main` / root**.

## Feedback from Part 2 and How It Was Addressed
| Part 2 feedback | Action taken |
|-----------------|--------------|
| README was well-detailed but lacking comprehension | Added live link, repository structure, Part 3 feature documentation, feedback table, and technologies list |
| Changelog was present but could be improved | Rewrote with one entry per change, listing the file, what changed, why, and whether it was feedback-related |
| No references provided | Added a References section to this README listing every source used |

## Technologies Used
HTML5, CSS3 (Grid, Flexbox, media queries), JavaScript (ES6, Fetch API, IntersectionObserver), Google Maps embeds, Git and GitHub, GitHub Pages, VS Code.

## Changelog
Format: **date, file(s): what changed and why.** Entries marked *(feedback)* respond to Part 2 marks.

### Part 3
- **[2026-10-29] all HTML files *(SEO)*:** Rewrote each page's meta keywords as natural phrases and worked every one into that page's visible text, so the keywords match the content.
- **[2026-10-29] `services.html`, `contact.html`, `about.html`, `enquiries.html` *(SEO)*:** Added Open Graph title, description and type tags (previously only on the home page) for better link previews.
- **[2026-10-29] `contact.html`, `js_assets/script.js`, `mystyles.css`:** Added an "Open in Gmail" link beside "Send email", so the compiled message can be sent from the browser on devices with no email app.
- **[2026-10-29] `enquiries.html`, `js_assets/script.js`:** Added a "How should we reply?" radio group, a stock-alert checkbox and a required consent checkbox, with validation for each; the quote now says whether we will reply by email or phone.
- **[2026-10-29] `contact.html`, `js_assets/script.js`:** Added a "Send me a copy" checkbox that adds the visitor's address as Cc on the compiled email.
- **[2026-10-29] `js_assets/script.js`, `mystyles.css`:** Rebuilt the lightbox with previous/next buttons, arrow-key navigation, an image counter and focus returning to the clicked photo.
- **[2026-10-29] all HTML files:** Shortened page titles to 60 characters or fewer so they are not cut off in search results.
- **[2026-10-29] `contact.html` *(fix)*:** Rebuilt the page. It was a copy of the enquiry page (wrong title, Google Form embed and no branch details); it now has both branches, a map and a validated contact form.
- **[2026-10-29] `index.html` *(fix)*:** Removed a duplicate `<!DOCTYPE html>` declaration so the page validates.
- **[2026-10-29] `index.html`, `_images/` *(feedback: responsive images)*:** Added a `<picture>` element with `srcset` and `sizes` for the hero image, using resized copies at 600px, 1000px and 1500px wide, so phones download a smaller file.
- **[2026-10-29] all HTML files, `_images/logo-100.png`, `_images/logo-200.png`:** Swapped the 2000×2000 (192 KB) logo for 100px and 200px versions with `srcset` (1x and 2x) to improve page speed.
- **[2026-10-29] all HTML files:** Replaced images that showed other businesses' branding with photos that suit a pet store, and matched each photo to its section with accurate alt text.
- **[2026-10-29] `README.md` *(feedback)*:** Restructured to add live link, Part 3 documentation, feedback table and technologies used, because the Part 2 README lacked comprehension.
- **[2026-10-29] `README.md` *(feedback)*:** Added References section with every source used, because Part 2 had none visible in the repository.
- **[2026-10-29] `js_assets/script.js`:** Created shared script with `catalogue` data, `$`/`$$` helpers and page initialisers.
- **[2026-10-29] `services.html`, `js_assets/script.js`:** Replaced static service cards with a list rendered from the `catalogue` array, adding search, category filter and price/name sorting.
- **[2026-10-29] `services.html`, `js_assets/script.js`:** Added FAQ accordion with `aria-expanded` for accessibility.
- **[2026-10-29] `index.html`, `js_assets/script.js`:** Added "Around the Store" gallery with lightbox overlay (Escape and click to close).
- **[2026-10-29] `mystyles.css`, `js_assets/script.js`:** Added scroll fade-in animation using IntersectionObserver, with a `prefers-reduced-motion` fallback.
- **[2026-10-29] `enquiries.html`, `js_assets/script.js`:** Replaced the Google Forms embed with an HTML form validated in JavaScript (required, email, phone, length, quantity, date) with inline error messages.
- **[2026-10-29] `enquiries.html`, `js_assets/script.js`:** Added `fetch` AJAX submission and a quote showing cost (price × quantity) and availability.
- **[2026-10-29] `contact.html`, `js_assets/script.js`:** Added contact form with the same validation; valid input is compiled into an email to the recipient set in `CONTACT_RECIPIENT`.
- **[2026-10-29] `contact.html`, `mystyles.css`:** Added a Google Maps embed for each branch (Hatfield and Centurion), using the keyless embed option so no API key or billing account is needed.
- **[2026-10-29] all HTML files:** Added unique `<title>` and meta description per page, one `<h1>` per page (site name moved to a `<p>`), and internal links in body text.
- **[2026-10-29] `_images/`:** Renamed images to descriptive names (for example `download (7).jpg` → `dog-haircut-at-grooming-salon.jpg`) and wrote descriptive alt text, width/height and lazy loading.
- **[2026-10-29] `contact.html`:** Added `PetStore` JSON-LD structured data for local SEO.
- **[2026-10-29] `robots.txt`, `sitemap.xml`:** Created to guide search engine crawlers.
- **[2026-10-29] `mystyles.css`:** Added form, accordion, lightbox, map, toolbar and focus-visible styles, plus responsive adjustments at 768px and 480px.
- **[2026-10-29] Deployment:** Published on GitHub Pages and added the live link to this README.

### Part 2 (summary)
- Built five HTML pages, linked `mystyles.css`, applied CSS reset, typography scale, Grid and Flexbox layout, hover/focus/active states, and media queries at 768px and 480px.

### Part 1 (summary)
- Wrote proposal, wireframes for five pages, sitemap and page content.

## References
> Replace the "Accessed" dates with the real dates you visited each source, and check the format against the IIE Referencing Guide.

Google, 2026. *Search Engine Optimization (SEO) Starter Guide*. [Online] Available at: https://developers.google.com/search/docs/fundamentals/seo-starter-guide [Accessed 29 October 2026].

Google, 2026. *Share or embed a map*. [Online] Available at: https://support.google.com/maps/answer/144361 [Accessed 29 October 2026].

GitHub, 2026. *GitHub Pages documentation*. [Online] Available at: https://docs.github.com/en/pages [Accessed 29 October 2026].

MDN Web Docs, 2026. *Fetch API*. [Online] Available at: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API [Accessed 29 October 2026].

MDN Web Docs, 2026. *Intersection Observer API*. [Online] Available at: https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API [Accessed 29 October 2026].


Sitemaps.org, 2026. *Sitemaps XML format*. [Online] Available at: https://www.sitemaps.org/protocol.html [Accessed 29 October 2026].

Typicode, 2026. *JSONPlaceholder: free fake REST API*. [Online] Available at: https://jsonplaceholder.typicode.com/ [Accessed 29 October 2026].

Canva, 2026. *Canva: logo design*. [Online] Available at: https://www.canva.com [Accessed 29 October 2026].

Unsplash, 2026. *Free high-resolution photos* (source of the photographs in `_images/`). [Online] Available at: https://unsplash.com [Accessed 29 October 2026].
