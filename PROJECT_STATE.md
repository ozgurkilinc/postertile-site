# TheOzLabs Canva Project State

Last updated: 2026-07-17

## Brand

- Company / publisher: TheOzLabs
- Developer: Ozgur Kilinc
- Support email: hello.theozlabs@gmail.com
- Public website repository: `ozgurkilinc/theozlabs-site`
- Current website base URL: `https://ozgurkilinc.github.io/theozlabs-site/`

## Canva app portfolio

| App | Status | Purpose |
|---|---|---|
| PosterTile | In Canva review | Splits large designs into printable pages |
| BookletFlow | In Canva review | Arranges pages for booklet printing |
| SheetNest | In Canva review | Packs mixed designs onto print sheets |
| SerialFlow | Draft / Preview working | Generates synchronized serial data for Bulk Create |

## SerialFlow confirmed state

- Canva Preview panel renders successfully.
- Design Editor intent is enabled.
- Data Connector must be enabled before full Bulk Create testing.
- Required scope: `canva:design:content` Read and Write.
- Production `app.js` is under 5 MB.
- `messages_en.json` is generated from the same build.
- Strict TypeScript check passed.
- Production build passed.
- Serial generator regression tests passed: 12/12.

## Final Canva package standard

Every final app package must include only the files required for submission and demonstration:

1. `app.js`
2. `messages_en.json`
3. 512 x 512 app icon
4. Up to two 2400 x 1800 featured images
5. Listing text
6. Company, terms, privacy, and support URLs
7. Reviewer testing instructions
8. Walkthrough video script
9. Demo assets needed to reproduce the review flow
10. QA and regression report

Never call a package final until the real production build, translation file, Canva Preview test, public URLs, and demo flow have been verified.

## Shared public URLs

- Company: `https://ozgurkilinc.github.io/theozlabs-site/`
- SerialFlow: `https://ozgurkilinc.github.io/theozlabs-site/apps/serialflow/`
- PosterTile: `https://ozgurkilinc.github.io/theozlabs-site/apps/postertile/`
- BookletFlow: `https://ozgurkilinc.github.io/theozlabs-site/apps/bookletflow/`
- SheetNest: `https://ozgurkilinc.github.io/theozlabs-site/apps/sheetnest/`
- Privacy: `https://ozgurkilinc.github.io/theozlabs-site/privacy/`
- Terms: `https://ozgurkilinc.github.io/theozlabs-site/terms/`
- Support: `https://ozgurkilinc.github.io/theozlabs-site/support/`

## Current incident: legacy review URLs return 404

The repository was renamed from `postertile-site` to `theozlabs-site`. GitHub redirects normal repository links after a rename, but it does not redirect GitHub Pages project-site URLs. The three apps already in review were submitted with URLs under:

- `https://ozgurkilinc.github.io/postertile-site/theozlabs/`
- `https://ozgurkilinc.github.io/postertile-site/theozlabs/terms/`
- `https://ozgurkilinc.github.io/postertile-site/theozlabs/privacy/`
- `https://ozgurkilinc.github.io/postertile-site/theozlabs/support/`

Those legacy URLs must be restored quickly to preserve the existing review queue.

Preferred repair: create a separate public compatibility repository named `postertile-site`, publish the legacy paths there, and keep `theozlabs-site` as the permanent clean website. Do not rename the permanent site again.

Fallback repair: temporarily rename `theozlabs-site` back to `postertile-site` until the three reviews finish. This restores the old project-site address but removes the clean URL.

Do not cancel all app submissions unless Canva requires a portal-field change. Submitted apps cannot be modified without canceling their submission.

## Release rules learned from failures

- Do not rename or move a live website after its URLs have been submitted to Canva.
- Use one permanent shared website domain or repository for all apps.
- Check every listing URL in a private browser before submission.
- Keep an automated daily URL health check.
- Keep a central app registry with app status, App ID, submitted URLs, build hash, and package version.
- Never bypass strict TypeScript errors just to produce a bundle.
- Verify the latest commit and workflow result before calling a package ready.
- Vercel deployment messages and Canva bundle build results are separate systems.
- Data Connector registration must not prevent the Design Editor UI from rendering.
- Invalid numeric input must show validation instead of blanking the app panel.

## New-chat continuity instruction

At the start of any future chat, ask ChatGPT to read this file from the GitHub repository and continue from the current project state. This file is the canonical project memory and must be updated whenever an app status, URL, package version, or submission decision changes.
