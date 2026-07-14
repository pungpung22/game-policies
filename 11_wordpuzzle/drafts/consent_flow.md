# Cipher Detective advertising consent flow

1. At commerce initialization, the Game asks UMP to update consent information.
2. UMP loads and shows a consent form when required for the user or region.
3. The Game checks `canRequestAds()` before initializing Google Mobile Ads.
4. When UMP reports that privacy options are required, Settings exposes the
   privacy-options entry point so the user can review choices.
5. Rewarded ads require an explicit user action. A native ad may load only for
   the exit-confirmation dialog and is skipped for Remove Ads owners.
6. If consent prevents ad requests, advertising remains unavailable without
   blocking core puzzle gameplay.

Recheck this flow and the AdMob Privacy & messaging configuration before every release.
