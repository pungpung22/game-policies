# SDK Data Inventory

Last updated: June 18, 2026

Use this inventory before every store submission. The privacy policy, Google Play Data safety form, and Apple App Privacy answers must match the exact SDKs enabled in the exported build.

## Current App Behavior

| Area | Current state | Notes |
| --- | --- | --- |
| Accounts | Not implemented | No login, email, username, profile, or cloud account. |
| Local save | Implemented | Saves progress, currencies, node graph, purchases owned, cooldowns, tutorial state, and privacy choices on device. |
| Ads | Implemented in mobile export path | Google AdMob test IDs are configured. Production IDs are still TODO. |
| Consent | In-app Privacy Bay implemented | Native Google UMP and iOS ATT are still TODO before personalized ads. |
| Purchases | Scaffolded | Product IDs exist in `data/shop_offers.json`; store console products and real transaction QA are still TODO. |
| Analytics | Off by default | No separate production analytics SDK should be enabled until consent and disclosure decisions are final. |
| Crash reporting | Not implemented separately | Add only after policy/store labels are updated. |
| Push notifications | Not implemented | No push token handling found. |
| Cloud save | Not implemented | Current save is local device storage. |
| Precise location | Not requested | No precise location permission requested by game code. Ad SDK may infer approximate location from IP address. |

## SDK / Provider Matrix

| Provider | Release status | Data categories to review | Purpose |
| --- | --- | --- | --- |
| Google Mobile Ads SDK / AdMob | Test IDs active; production IDs TODO | IP address, advertising/device identifiers, app interactions, diagnostics | Advertising, ad measurement, fraud prevention, frequency capping |
| Google User Messaging Platform | Required before personalized ads | Consent state and privacy choice signals | Privacy messages and consent management |
| Google Play Billing | Android scaffold present | Product ID, purchase token, purchase status, purchase history | Process Android digital goods and restore/grant entitlements |
| Apple StoreKit 2 | iOS plugin present | Product ID, receipt/transaction ID, transaction status, purchase history | Process iOS digital goods and restore/grant entitlements |
| Meta Audience Network mediation | iOS plugin file present; verify before release | Ad request and device/ad identifiers if enabled | Ad mediation |
| Liftoff/Vungle mediation | iOS plugin file present; verify before release | Ad request and device/ad identifiers if enabled | Ad mediation |

## Data Not Currently Collected By The App Itself

- Name
- Email address
- Phone number
- Contacts
- Photos or videos
- Camera or microphone recordings
- Precise location
- Health or fitness data
- Messages or user-generated public content

## Build Review Checklist

- Confirm production AdMob IDs or keep test-only build.
- Confirm whether mediation frameworks are actually enabled in the exported iOS project.
- Confirm Google Play and App Store product IDs match `data/shop_offers.json`.
- Confirm Privacy Bay appears on first launch and after policy-version changes.
- Confirm personalized ads remain locked until native UMP/ATT is complete.

