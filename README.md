# The No-Ops HubSpot Gap Checklist

An interactive, evidence-led self-assessment for teams running HubSpot without a dedicated RevOps, SalesOps, or MarketingOps owner.

## GitHub Pages

This repository is a static website. The production entry point is `index.html`; no build step is required.

To publish it:

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select the `main` branch and `/ (root)` folder.
4. Save and wait for GitHub Pages to publish the site.

The default Pages URL will be:

`https://mikesachs-gtm.github.io/The-No-Ops-HubSpot-Gap-Checklist/`

## Tracking status

The production domain is `https://hubspotchecklist.gtmdiagnostics.com`.

The site uses a consent-first tracking model:

- HubSpot portal `27209634` is installed directly so its consent banner can load on the external domain.
- Google Consent Mode v2 defaults analytics and advertising consent to denied.
- Google Tag Manager container `GTM-KNVS78KV` is requested only after the HubSpot `advertisement` category is explicitly granted.
- The GTM container currently contains only the Apollo visitor tracker.
- Consent changes are published to the data layer as `hubspotConsentUpdate`.
- A Cookie settings control in the footer reopens the HubSpot banner.
- The GTM `<noscript>` iframe is deliberately omitted because it cannot wait for JavaScript-based consent.

Required platform configuration:

- In HubSpot, target `hubspotchecklist.gtmdiagnostics.com` with a cookie-by-category opt-in banner that includes the Advertisement category.
- In Apollo Website Visitors, add `https://hubspotchecklist.gtmdiagnostics.com` and use Apollo's connection test.
- Keep the Apollo script intact inside GTM. The website controls when the container can load.
- Test acceptance, rejection, and preference changes with Google Tag Assistant, HubSpot tracking diagnostics, Apollo's connection test, and a clean incognito session.

## Local behavior

Assessment scores and notes are stored only in the visitor's browser using `localStorage`. They are not submitted to GitHub, HubSpot, Apollo, or any other service.
