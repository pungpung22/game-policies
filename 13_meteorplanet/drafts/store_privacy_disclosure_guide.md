# Tide Paws App Store privacy disclosure guide

This is a conservative release checklist, not the public privacy policy. Confirm
every answer against the exact archived binary and current SDK vendor disclosures.

## App Store Connect candidate data types

| Apple data type | Why it may be collected | Purpose to review | Linked/tracking review |
| --- | --- | --- | --- |
| Coarse Location | AdMob can infer it from IP | Third-Party Advertising, Analytics | Confirm Google's current answer |
| Device ID | AdMob may use advertising or app/developer-bounded identifiers | Third-Party Advertising, Analytics, Fraud Prevention | Tracking depends on consent/configuration; do not guess |
| Purchase History | StoreKit and developer verifier process product and transaction ids | App Functionality, Fraud Prevention | Transaction is linked to store context; conservatively review as linked |
| Product Interaction | AdMob can process launches, taps and video views | Third-Party Advertising, Analytics | Review SDK configuration |
| Advertising Data | Ads shown and interaction/completion | Third-Party Advertising, Analytics | Review SDK configuration |
| Crash Data | AdMob SDK diagnostics | Third-Party Advertising, Analytics/App Functionality | Review SDK disclosure |
| Performance Data | Launch time, hangs, energy or SDK performance | Third-Party Advertising, Analytics/App Functionality | Review SDK disclosure |

Gameplay progress stored only on the device is not developer collection. Payment
card information entered in Apple's purchase sheet is not collected by the app or
developer. Optional support email may qualify for Apple's optional-disclosure rule
only when all of Apple's conditions are satisfied; confirm rather than assuming.

## Tracking answer

The current iOS export has no ATT usage description and its app privacy manifest
declares tracking false. Answer “Data Used to Track You: No” only if the production
AdMob setup, consent messages, SDK privacy manifests and Xcode Privacy Report all
confirm that no data is linked across third-party apps/websites for advertising or
measurement. Otherwise add a compliant ATT flow and update code, policy and labels.

## App Store URLs

- Privacy Policy URL: `https://pungpung22.github.io/game-policies/13_meteorplanet/privacy/`
- Support URL: `https://pungpung22.github.io/game-policies/13_meteorplanet/support/`
- Marketing/policy hub: `https://pungpung22.github.io/game-policies/13_meteorplanet/`

## Review notes and gates

- Explain that all advertisements are user-initiated rewarded placements.
- Explain that Support License skips the video while retaining placement caps.
- Submit all seven IAPs with the binary and keep them visible to review.
- Provide a working Restore Purchases control for non-consumables.
- Paid buttons must use a live HTTPS verifier during review; no placeholder endpoint.
- Add an easily accessible privacy-policy link inside the game.
- Add a settings entry that reopens UMP privacy choices when required.
- Verify that purchased Tide Cores do not expire and no paid random loot exists.

## Authoritative references checked 2026-07-14

- Apple App privacy: https://developer.apple.com/help/app-store-connect/reference/app-privacy/
- Apple privacy details: https://developer.apple.com/app-store/app-privacy-details/
- Apple App Review Guidelines: https://developer.apple.com/app-store/review/guidelines/
- Google Mobile Ads data disclosure: https://developers.google.com/ad-manager/mobile-ads-sdk/ios/privacy/data-disclosure
- Google UMP for iOS: https://developers.google.com/admob/ios/privacy
