# WhimziLab — My Little World website

Public parent/guardian support and privacy pages for **My Little World: Create & Play**.

- Home: https://whimzilab.com/
- iOS privacy policy: https://whimzilab.com/privacy/
- Support: https://whimzilab.com/support/
- Public support/privacy email: whimzilab@gmail.com

## Hosting and maintenance

This repository is the source for the **GitHub Pages** website. Porkbun is the domain registrar. `CNAME` contains `whimzilab.com`; `.nojekyll` preserves plain static serving. Keep both files when updating the site. The earlier OpenAI Sites copy is a separate deployment; changing this repository does not update or remove that copy.

The site is plain HTML and CSS with local image assets; no build or package installation is required. Pages are `index.html`, `privacy/index.html` and `support/index.html`. Shared styling is in `styles.css`. Paths beginning with `/` resolve against the custom domain.

For local preview, run `python3 -m http.server 4181` from the repository root and open `http://localhost:4181/`. Check all three pages, local links and section anchors before publishing changes. Do not add analytics, contact forms or external embeds without reviewing their privacy impact and updating the policy.

## Privacy wording review — 23 September 2026

The live privacy page returned HTTP 200 with `server: GitHub.com`. Repository metadata also confirms Pages is enabled and `CNAME` matches the custom domain. The former OpenAI Sites/Cloudflare hosting paragraph has been replaced with GitHub Pages' documented IP-address logging for security, and the policy revision date updated.

Sources:

- [GitHub Pages data collection](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages#data-collection)
- [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement)

The website source contains no added scripts, registration or contact forms. This source review does not certify all provider behavior or the final native app. The policy covers iOS only; Android requires its own review. Verify policy statements whenever the app, hosting or support practices change.

The published App Store name is used on these pages; this does not assert that the app has completed App Review or is publicly released. App Store Connect and native app links must be maintained separately.
