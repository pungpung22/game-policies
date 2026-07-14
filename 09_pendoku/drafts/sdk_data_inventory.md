# Pengudoku SDK and data inventory

| Component | Platforms | Role | Possible data | Control/notes |
| --- | --- | --- | --- | --- |
| Google Mobile Ads (AdMob) | Android, iOS | Rewarded and interstitial ads | IP, coarse location, device/app identifiers, ad data, interactions, diagnostics | Ads initialize only after UMP flow is ready |
| Google User Messaging Platform | Android, iOS | Consent and privacy options | Consent state, device/app context | Privacy options can be reopened when available |
| Firebase Analytics | Android, iOS | Optional usage analytics | App instance ID, device/app info, coarse region, gameplay events | Disabled by default; user setting enables it |
| Firebase Crashlytics | Android, iOS | Optional crash diagnostics | Crash stack, device/app info, performance and custom stage context | Disabled by default; user setting enables it |
| Firebase Remote Config | Android, iOS | Optional update notice configuration | Firebase installation identifier, app/OS/device and technical request information | Always available for app functionality; no progress, currency or account data sent |
| Apple StoreKit / Google Play Billing | iOS, Android | In-app purchase and restore | Product ID, transaction/purchase status, store account context | Store handles payment details |
| Native review prompt | Android, iOS | App rating request | Platform-controlled | Requested after qualifying clears; no review text read by app |
| GitHub Pages | Web | Policy and support hosting | Standard web request data handled by GitHub | No game account linkage |

## Local save inventory

Progress, best times, stars, tutorial and attendance state, fish and item balances,
rewarded-ad date/count, selected/unlocked/purchased skins, purchase product state,
review prompt state, sound, haptics and optional analytics setting.

## Release audit

1. Compare exported Android and iOS plugin lists with this table.
2. Check package ID and all store product IDs.
3. Check UMP form access and ATT behavior on physical devices.
4. Confirm Firebase remains disabled before opt-in and stops after opt-out.
5. Update public policy and store privacy forms before shipping SDK behavior changes.
