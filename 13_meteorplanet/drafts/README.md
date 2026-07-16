# Tide Paws policy source

Store-review and public-policy source material for **Tide Paws: Abyss Drillers**
(`com.overdrill.planetbreaker`).

Published pages:

- Privacy: <https://pungpung22.github.io/game-policies/13_meteorplanet/privacy/>
- Terms: <https://pungpung22.github.io/game-policies/13_meteorplanet/terms/>
- Support: <https://pungpung22.github.io/game-policies/13_meteorplanet/support/>

Before every release, compare these documents with the submitted binary, AdMob
configuration, UMP consent flow, StoreKit products, purchase-verification host,
local save schema, permissions and support address.

## Current release gates found on 2026-07-14

- The production purchase-verification host is not selected. Add its operator,
  country, retention period and deletion process before enabling paid products.
- The iOS AdMob app and opt-in rewarded unit are configured. The Android app id
  and rewarded unit remain intentionally unset until the Android AdMob app exists.
- Settings now links to the public privacy/support pages and can reopen the UMP
  form when it is available. Confirm every regional path on a physical device.
- The client gates ad initialization on UMP `NOT_REQUIRED` or `OBTAINED` status,
  including update/form failure paths. Device-test this against the final archive.
- Decide whether the title is directed to children. Configure AdMob child-directed
  treatment and the App Store age rating consistently with that decision.
- Re-run Xcode Privacy Report and compare every embedded SDK privacy manifest
  with `store_privacy_disclosure_guide.md` before submission.

These files are an operational draft, not a substitute for advice from a
qualified privacy or consumer-law professional.
