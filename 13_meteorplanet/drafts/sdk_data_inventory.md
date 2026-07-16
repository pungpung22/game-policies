# Tide Paws SDK and data inventory

| Component | Platforms | Role | Possible data | Control/notes |
| --- | --- | --- | --- | --- |
| Google Mobile Ads 12.14.0 | iOS, Android | Opt-in rewarded ads | IP/coarse location, device or app identifier, ad data, app/ad interactions, crash and performance data | iOS production app/rewarded ids configured; Android pending; no forced interstitial or banner |
| Google UMP 3.1.0 | iOS, Android | Consent and privacy choices | Consent state and device/app context | Ad requests gated on `NOT_REQUIRED`/`OBTAINED`; Settings exposes privacy choices when the form is available |
| Apple StoreKit 2 | iOS | Product lookup, purchase and restore | Product id, transaction/original transaction id, signed transaction, status, store account context | Card data remains with Apple; client finishes only after server verification |
| Google Play Billing | Android | Product lookup, purchase and restore | Product id, purchase token/status, Play account context | Android later; card data remains with Google |
| Developer purchase verifier | iOS, Android | Receipt validation, fulfillment, deduplication, refund security | Product and transaction ids, Apple JWS or Play token, app id, IP/technical request logs | Hosting provider, region and retention TBD; paid buttons disabled until HTTPS endpoint exists |
| Local AnalyticsService | iOS, Android | In-memory debugging | Up to 80 gameplay/BM events and payloads | No network transport and not persisted by this service |
| GitHub Pages | Web | Policy/support hosting | Standard web request data handled by GitHub | No automatic game-account linkage |
| Email/GitHub Issues | Web/email | Voluntary support | Email, problem description, optional device/app details, screenshot, partial order id | GitHub issues are public; users warned not to post sensitive data |

## Local save inventory

Stage and boss progress; currencies; upgrades; research; cards; collection;
equipped drill and pilot; settings; aggregate and daily stats; purchases and
entitlements; processed/pending transaction ledgers; season pass; boosts;
rewarded-ad counts/timestamps; daily claims; last-seen timestamp.

## Not present in the current game

- Account/login, cloud save or developer user profile
- Firebase Analytics, Crashlytics or Remote Config
- Camera, microphone, contacts, photos or precise-location access
- User-generated gameplay content or chat
- Forced interstitial advertising or banners
- ATT prompt or deliberate IDFA use

## Release audit

1. Compare the exact Xcode archive SDKs and privacy manifests with this table.
2. Confirm the configured iOS AdMob identifiers against the final archive and
   record the future Android identifiers plus purchase-verifier operator.
3. Confirm UMP status gating, privacy-options reopening and child-directed settings.
4. Verify the app's in-game privacy and support links.
5. Reconcile App Store privacy labels before every version submission.
