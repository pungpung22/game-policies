# Cipher Detective SDK and data inventory

Verified against the Flutter project on July 16, 2026.

## Packages that affect disclosure

| Package or service | Current use | Data or state involved |
| --- | --- | --- |
| `shared_preferences` | Local progress and settings | Progress, ink, content ownership, settings, purchase fulfillment keys |
| Google Mobile Ads | Rewarded ads and exit native ad | IP/coarse location, identifiers, interactions, diagnostics, device/app/network data |
| Google UMP | Regional advertising consent | Consent status and privacy choices |
| Apple App Tracking Transparency | iOS tracking permission | Tracking authorization status and access control for the advertising identifier |
| RevenueCat `purchases_flutter` | Store products, validation, restoration, and Detective Pass | Anonymous app user ID, product and transaction identifiers, purchase history, subscription status |
| `in_app_review` | Milestone review prompt | Store/provider-controlled review flow |

## Not present

- No account, login, developer API, cloud save, Firebase, social login, or user-generated content.
- No camera, microphone, contacts, photos, precise location, health, messages, or address-book access.
- `AnalyticsService` stores a short event list only in app memory and does not transmit events.

## Ad behavior

- Rewarded ads are user initiated for bonuses or failure continuation.
- A native ad can appear in the exit-confirmation dialog.
- Detective Pass hides non-optional advertising while active; rewarded choices remain available.
- Interstitial support exists in the service layer, but no current UI/controller path requests it.
- No ad request is allowed while actively solving a puzzle.
