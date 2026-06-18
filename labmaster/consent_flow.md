# Consent Flow

Last updated: June 18, 2026

This file tracks the privacy and consent flow required for Labmaster builds.

## Current In-App Flow

- First launch blocks play with Privacy Bay before tutorial, ad, analytics, or store-service choices.
- The required gate is for privacy/terms review only; optional personalized ads and analytics consent must remain freely selectable.
- Privacy defaults are non-personalized ads and analytics off.
- Personalized ads are locked until native Google UMP and iOS ATT handling are integrated.
- Policy version is `2026-06-18`.
- If the policy version changes, the app should require Privacy Bay review again.
- Players can review or reset choices from Shop -> Privacy Choices.

## Native Consent Work Still Required Before Personalized Ads

Do not unlock personalized ads until all items below are implemented and tested:

- Google User Messaging Platform consent info update on app start.
- Google UMP consent form display where required.
- Ad requests gated by the platform consent status.
- iOS App Tracking Transparency prompt before accessing IDFA or tracking across apps/sites.
- Store privacy disclosures updated to match the final SDKs and purposes.
- Clean-install QA in at least the United States, EEA/UK, and a non-EEA region if possible.

## Test Cases

- Fresh install opens Privacy Bay before tutorial.
- Close, Lab, Goals, and Shop cannot bypass the required first-run Privacy Bay.
- Reviewed records the current policy version.
- Reset Choices returns ads to non-personalized and analytics off.
- Changing the policy version requires review again.
- Attempting to enable personalized ads keeps it locked until native UMP/ATT is integrated.
- Rewarded ads remain optional.
- Remove Ads does not hide rewarded choices unless the design explicitly changes.
