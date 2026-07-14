# Cipher Detective SDK and data inventory

Verified against the Flutter project on July 14, 2026.

## Packages that affect disclosure

| Package or service | Current use | Data or state involved |
| --- | --- | --- |
| `shared_preferences` | Local progress and settings | Progress, ink, content ownership, settings, purchase fulfillment keys |
| Google Mobile Ads | Rewarded ads and exit native ad | IP/coarse location, identifiers, interactions, diagnostics, device/app/network data |
| Google UMP | Regional advertising consent | Consent status and privacy choices |
| `in_app_purchase` | Store products and restoration | Product, purchase status, verification, and transaction identifiers |
| `in_app_review` | Milestone review prompt | Store/provider-controlled review flow |

## Not present

- No account, login, developer API, cloud save, Firebase, social login, or user-generated content.
- No camera, microphone, contacts, photos, precise location, health, messages, or address-book access.
- `AnalyticsService` stores a short event list only in app memory and does not transmit events.

## Ad behavior

- Rewarded ads are user initiated for bonuses or failure continuation.
- A native ad can appear in the exit-confirmation dialog.
- Remove Ads hides non-optional advertising; rewarded choices remain available.
- Interstitial support exists in the service layer, but no current UI/controller path requests it.
- No ad request is allowed while actively solving a puzzle.
