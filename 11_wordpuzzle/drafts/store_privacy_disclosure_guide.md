# Cipher Detective store privacy disclosure guide

This is a release checklist, not the public privacy policy. Reconfirm every answer
in App Store Connect and Google Play Console against the exact submitted binary
and the SDK-provider disclosures current on the submission date.

## Data handled by the app or SDKs

| Category | Default behavior | Purpose | Linked to identity |
| --- | --- | --- | --- |
| Local gameplay and settings | Stored on device | App functionality | No game account |
| IP address and coarse location | Google Mobile Ads may process | Advertising, analytics, fraud prevention | Review Google definition |
| Device or account identifiers | Google Mobile Ads may process | Advertising, analytics, fraud prevention | Review provider/platform definition |
| Product and ad interactions | Google Mobile Ads may process ad/app interactions | Advertising and measurement | No Developer-set user ID |
| Diagnostics | Google Mobile Ads may process SDK/app diagnostics | Advertising, analytics, security | No Developer-set user ID |
| Product and transaction identifiers | Store billing and local fulfillment | Purchase delivery, restoration, duplicate prevention | Store account controls linkage |
| Anonymous app user ID, purchase history, and subscription status | RevenueCat purchase SDK | Validation, entitlement access, restoration, fraud prevention, diagnostics | RevenueCat customer record |

## Google Play Data safety review points

- Declare collection and sharing required by the current Google Mobile Ads SDK disclosure.
- Expected categories include approximate location, device or other identifiers,
  app interactions, advertising data, and diagnostics. Confirm names and purposes
  in the current Play Console form.
- Data is encrypted in transit by Google Mobile Ads according to Google's disclosure.
- Purchases use Google Play Billing through RevenueCat on Android.
- Users can delete complete local data by clearing app storage or uninstalling.
- There is no account creation, so the app account-deletion requirement does not apply.
- Privacy Policy URL: `https://pungpung22.github.io/game-policies/11_wordpuzzle/privacy/`

## App Store Connect review points

- The Game does not request contact details, precise location, contacts, photos,
  camera, microphone, health data, or user-generated content.
- Purchases are handled through StoreKit via RevenueCat; RevenueCat processes an
  anonymous app user ID, product and transaction identifiers, purchase history,
  and subscription status for validation and restoration.
- Review identifiers, usage data, diagnostics, and tracking answers against the
  current Google Mobile Ads iOS privacy disclosure and the final consent setup.
- Do not claim that the app collects no data solely because gameplay stays local.
- The current app does not request ATT. Re-evaluate before submission if the
  advertising configuration or tracking behavior changes.
