# SDK Data Inventory

Last updated: June 18, 2026

Use this inventory before every store submission. The privacy policy, Google Play Data safety form, and Apple App Privacy answers must match the exact SDKs enabled in the exported build.

## Current App Behavior

| Area | Current state | Notes |
| --- | --- | --- |
| Accounts | Not implemented | No login, email, username, profile, or cloud account. |
| Local save | Implemented | Saves progress, currencies, upgrades, purchase flags, offline reward state on device. |
| Ads | Implemented in mobile export path | `scripts/AdService.gd` uses Google Mobile Ads rewarded ads on Android/iOS. Desktop shows no ads. |
| Consent | Plugin available, app flow still TODO | Google UMP plugin exists in `addons/admob`; production flow still needs integration before privacy-sensitive launch regions. |
| Purchases | Placeholder gameplay grants exist | Shop data has product IDs, but platform billing and receipt verification are still TODO. |
| Analytics | Not implemented separately | No Firebase Analytics or custom analytics found. Ad SDK may provide ad interaction analytics. |
| Crash reporting | Not implemented separately | No Firebase Crashlytics/Sentry found. Ad SDK may process diagnostics. |
| Push notifications | Not implemented | No push token handling found. |
| Cloud save | Not implemented | Current save is local device storage. |
| Precise location | Not requested | No precise location permission found. Ad SDK may infer approximate location from IP address. |

## SDK / Provider Matrix

| Provider | Release status | Data categories to review | Purpose |
| --- | --- | --- | --- |
| Google Mobile Ads SDK / AdMob | Active for Android/iOS rewarded ads | IP address, advertising/device identifiers, user product interactions, diagnostics | Advertising, ad measurement, analytics, fraud prevention |
| Google User Messaging Platform | Plugin present, consent flow TODO | Consent state and privacy choice signals | Privacy messages and consent management |
| Google Play Billing | Planned | Product ID, purchase token, purchase status, purchase history | Process Android digital goods and restore/grant entitlements |
| Apple StoreKit | Planned | Product ID, receipt, transaction status, purchase history | Process iOS digital goods and restore/grant entitlements |
| Meta Audience Network mediation | iOS plugin file present, verify before release | Ad request and device/ad identifiers if enabled | Ad mediation |
| Liftoff/Vungle mediation | iOS plugin file present, verify before release | Ad request and device/ad identifiers if enabled | Ad mediation |

## Data Not Currently Collected By The App Itself

- Name
- Email address
- Phone number
- Contacts
- Photos or videos
- Camera or microphone recordings
- Health or fitness data
- Precise GPS location
- User-generated public content
- Account credentials
- Payment card details

## Required Before Production Submission

- Replace test AdMob unit IDs with production IDs.
- Add UMP consent flow for regions where Google requires privacy messaging.
- Add iOS ATT prompt only if IDFA/cross-app tracking is used.
- Add platform billing and receipt verification before enabling paid IAP.
- Confirm whether Meta and Liftoff/Vungle mediation are actually enabled; remove from disclosure if not included.
- Fill final Google Play Data safety and Apple App Privacy answers from the release build, not from planned features.
- Public policy URLs have been assigned under `https://pungpung22.github.io/game-policies/01_crushfactory/`.
