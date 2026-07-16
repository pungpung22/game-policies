# Cipher Detective advertising consent flow

1. At commerce initialization, the Game asks UMP to update consent information.
2. UMP loads and shows a consent form when required for the user or region.
3. On iOS, the published AdMob IDFA message can explain the request before
   Apple's ATT prompt. If ATT status is undetermined, the system prompt is shown
   before access to the advertising identifier or tracking. Denial does not
   block core gameplay or non-tracking ad requests.
4. The Game checks `canRequestAds()` before initializing Google Mobile Ads.
5. When UMP reports that privacy options are required, Settings exposes the
   privacy-options entry point so the user can review choices.
6. Rewarded ads require an explicit user action. A native ad may load only for
   the exit-confirmation dialog and is skipped while Detective Pass is active.
7. If consent prevents ad requests, advertising remains unavailable without
   blocking core puzzle gameplay.

Users can review UMP privacy choices from the in-game Settings entry point when
required and can change ATT permission in iOS Settings under Privacy & Security
> Tracking. Test both ATT acceptance and denial on a clean install.

Recheck this flow and the AdMob Privacy & messaging configuration before every release.
