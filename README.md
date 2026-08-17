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

No marketing or analytics tracking code is included yet. Add the Google Tag Manager container only after the consent configuration and production domain have been confirmed.

Recommended deployment model:

- Load HubSpot and Apollo tracking through Google Tag Manager.
- Use the HubSpot consent banner on the external production domain.
- Default Google Consent Mode v2 to denied in the relevant regions.
- Require the appropriate HubSpot consent category before third-party tags fire.
- Test with Google Tag Assistant, HubSpot tracking diagnostics, Apollo's connection test, and a clean incognito session.

## Local behavior

Assessment scores and notes are stored only in the visitor's browser using `localStorage`. They are not submitted to GitHub, HubSpot, Apollo, or any other service.
