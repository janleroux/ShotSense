# Release notes
## Version 0
### v0.3
* Code Copilot to refactor the ESP32 OTA update code into a modular, cleaner, more configurable version with improved error handling and configurable intervals.

Plan (pseudocode)
1. Configuration Section
* Store WiFi credentials, URLs, and firmware version.
* Allow update check interval to be set in seconds (not arbitrary loop count).

2. WiFi Manager
* connectToWiFi() separated and reusable.
* Add retries and error messages.

3. Update Manager
* checkForFirmwareUpdate() orchestrates update steps.
* fetchLatestVersion() only gets version text.
* downloadAndApplyFirmware() handles fetching .bin.
* startOTAUpdate() writes binary data with timeout and progress.

4. Main Loop
* Non-blocking update scheduler with millis() instead of fixed countdown decrement.
* Error Handling
* Fail gracefully with messages (no silent fails).
* Consistent return codes (true/false).

### v0.2
* increase updateCheckInterval to 48
  
### v0.1
* origin
