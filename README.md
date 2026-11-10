# WhimziLab — My Little World website

Public parent/guardian support and privacy pages for **My Little World: Create & Play**.

- Home: https://whimzilab.com/
- iOS and Android privacy policy: https://whimzilab.com/privacy/
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

The website source contains no added scripts, registration or contact forms. This source review does not certify all provider behavior or the final native app. At that revision, the policy covered iOS only. See the Android update below. Verify policy statements whenever the app, hosting or support practices change.

The published App Store name is used on these pages; this does not assert that the app has completed App Review or is publicly released. App Store Connect and native app links must be maintained separately.

## Android coverage — 29 September 2026

The privacy page now covers the native iOS and Android apps, including test versions. The home and support pages use the same scope. Existing URLs and section anchors are preserved.

The Android section describes Google Play Billing, product/price and ownership checks, purchase-token acknowledgement, the signed local purchase record, store-provider processing and Android backups. It keeps local saved play distinct from store records, website hosting and emailed support. Purchases and restoration are described conditionally: the reviewed Android build still has empty product/key configuration. This website update does not claim Google Play release or successful purchase testing.

Evidence reviewed in `sasano-cc/My-little-world` at commit `0e184cbf2f04a42c72d5dd90b460a34ab198258e`:

- `android/app/src/main/java/com/mylittleworld/preview/FullWorldPlugin.java`: Play Billing requests; receipt stored in `noBackupFilesDir`; receipt replacement/deletion; ownership refresh on resume; no child identifier supplied to billing and no publisher purchase server.
- `android/app/src/main/AndroidManifest.xml`: `allowBackup=true`.
- `android/app/build.gradle`: Google Play Billing 9.1.0.
- `android/app/src/main/res/values/billing.xml`: purchase configuration not yet supplied.

References:

- [Google Play Billing integration](https://developer.android.com/google/play/billing/integrate)
- [Android Auto Backup](https://developer.android.com/identity/data/autobackup)
- [Google privacy policy](https://policies.google.com/privacy)
- [Play privacy-policy guidance](https://support.google.com/googleplay/android-developer/answer/9859455)

**Remaining release work:** verify the final Android build's SDK/diagnostic network traffic, including Billing's DataTransport dependency, and its actual backup/transfer behavior. Reconcile any specific data types and retention practices found with this policy and Play's Data safety declaration before app submission. A source review and policy update do not establish that no data is collected. Revisit the policy if a verification backend, SDK, account system or other data handling is added.

## Android Google Play Billing update — 10 November 2026

The privacy page's "On Android" section (now anchored `#android`) describes Android build 22 and later. Those builds connect to Google Play only while Grown-ups is open after the number question, or for follow-up checks on an unfinished purchase a grown-up started. The section adds what Google Play Billing 9.1.0 sends to Google automatically, and how that appears in Play's Data safety section. The saved-world and privacy-rights sections each gained one sentence pointing to it. The wording comes from `docs/GOOGLE-PLAY-PRIVACY-DRAFTS-2026-11-06.md` in `sasano-cc/My-little-world`; the Billing gate is commit `f8539a2`.

- Keep "How this appears on Google Play" matched to the Data safety answers submitted in Play Console. Google's User Data policy requires the two to agree.
- The wording about when Billing runs is true only for builds 22 and later. On 10 November Play Console showed build 23 on internal testing, and build 15 in a closed-testing release that was never sent for review. Replace build 15 there before sending anything for review.
- Review the section when Google answers [Issue 572483462](https://issuetracker.google.com/issues/572483462).
