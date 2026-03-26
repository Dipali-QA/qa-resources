# 📱 Mobile Testing Checklist

> Comprehensive checklist for testing mobile applications on Android and iOS.
> Use for every release cycle — check off each item after verification.

**Author:** Dipali Pagire | QA Engineer | Pune, India  
**Tools Used:** Manual testing, BrowserStack, Appium (where applicable)

---

## 📋 Test Details

| Field           | Value                             |
|-----------------|-----------------------------------|
| App Name        | [Application Name]                |
| App Version     | [v1.0.0]                          |
| Tested By       | [Name]                            |
| Test Date       | [DD-MM-YYYY]                      |
| Devices Tested  | [List all devices used]           |
| OS Versions     | [Android 13, iOS 17, etc.]        |

---

## 1. 📲 Installation & Launch

- [ ] App installs successfully from APK / App Store / TestFlight
- [ ] App icon appears correctly on home screen
- [ ] App launches without crash on first open
- [ ] App launches within acceptable time (under 4 seconds)
- [ ] Splash screen / loading screen displays correctly
- [ ] App does not request unnecessary permissions on install
- [ ] Permission prompts appear at the right time (not all at once on launch)
- [ ] App uninstalls cleanly with no residual files/data
- [ ] App reinstalls correctly after uninstall

---

## 2. 🔐 Login & Authentication

- [ ] Login screen displays correctly on all target screen sizes
- [ ] Valid credentials allow login
- [ ] Invalid credentials show clear error message
- [ ] "Remember me" / "Stay logged in" works correctly
- [ ] Session persists when app is backgrounded and reopened
- [ ] Session expires correctly after inactivity timeout
- [ ] Logout clears session and redirects to login screen
- [ ] Biometric login (fingerprint / Face ID) works where implemented
- [ ] Password field masks characters (shows dots/asterisks)
- [ ] "Show password" toggle works correctly
- [ ] Deep links open correct screens (for apps with deep linking)

---

## 3. 📐 UI & Layout

- [ ] All text is readable and not truncated on any target screen size
- [ ] Buttons, icons, and touch targets are large enough (minimum 44x44pt / 48x48dp)
- [ ] UI renders correctly in portrait orientation
- [ ] UI renders correctly in landscape orientation (if supported)
- [ ] No overlapping UI elements
- [ ] No content cut off at screen edges
- [ ] Images and icons are sharp (not pixelated) on all screen densities
- [ ] Font sizes are legible — no text is too small to read
- [ ] Colour contrast meets accessibility standards
- [ ] UI is consistent with the approved design specs
- [ ] Dark mode renders correctly (if supported)
- [ ] Placeholder text appears in empty input fields
- [ ] Error states display correctly (red borders, error messages)
- [ ] Loading spinners/skeletons appear during data fetch

---

## 4. ⌨️ Forms & Input

- [ ] Correct keyboard type opens for each field (numeric, email, text, phone)
- [ ] Keyboard does not obscure active input fields
- [ ] "Next" button on keyboard moves focus to next field
- [ ] "Done" / "Go" button on keyboard submits form where applicable
- [ ] Auto-fill / auto-suggest works correctly
- [ ] Auto-correct behaviour is appropriate for each field type
- [ ] Copy-paste works in all input fields
- [ ] Character limits are enforced where defined
- [ ] Required fields are clearly marked
- [ ] Validation errors appear inline below relevant fields
- [ ] Date pickers, dropdown selectors, and pickers work correctly
- [ ] Search field returns correct results in real time or on submit

---

## 5. 🔄 Navigation & Gestures

- [ ] Back button (Android hardware / iOS swipe) navigates correctly
- [ ] Bottom navigation / tab bar switches sections correctly
- [ ] Swipe gestures work as designed (swipe to delete, swipe to go back)
- [ ] Pull-to-refresh updates content correctly
- [ ] Scroll works smoothly without stuttering
- [ ] Lists scroll to top correctly when tapping the status bar (iOS)
- [ ] Modal / bottom sheets open and close correctly
- [ ] Nested scroll views work without conflicts
- [ ] No navigation dead ends (user can always go back or home)

---

## 6. 🌐 Network Conditions

- [ ] App works correctly on WiFi
- [ ] App works correctly on 4G/LTE
- [ ] App works correctly on 3G (slower network)
- [ ] App handles network loss gracefully (shows "No internet" message)
- [ ] App recovers when network is restored (without requiring full restart)
- [ ] App does not crash when switching between WiFi and mobile data
- [ ] API timeout errors show user-friendly messages (not technical errors)
- [ ] App handles slow responses gracefully (loading states, retry options)
- [ ] Offline mode works correctly where implemented (cached data shown)
- [ ] Data sync works correctly after coming back online

---

## 7. ⚡ Performance

- [ ] App launches within 4 seconds on target devices
- [ ] Screens load within 2–3 seconds on standard connection
- [ ] Scrolling is smooth (60fps) — no jank or dropped frames
- [ ] No memory leaks (app doesn't slow down over extended use)
- [ ] App does not overheat the device during normal use
- [ ] Battery consumption is not excessive during standard use
- [ ] Large data sets (100+ items) load with pagination without freezing
- [ ] Images load progressively (not causing layout jumps)
- [ ] App size is reasonable (not bloated with unused assets)

---

## 8. 🔔 Notifications

- [ ] Push notifications are received correctly
- [ ] Notification content is correct (title, body, icon)
- [ ] Tapping a notification navigates to the correct screen
- [ ] Notifications are not received when the user has opted out
- [ ] In-app notifications/banners display correctly
- [ ] Notification badge count on app icon is accurate
- [ ] Notifications work in background state
- [ ] Notifications work in killed/closed app state

---

## 9. 🔒 Permissions

- [ ] App requests camera permission only when camera feature is used
- [ ] App requests location permission only when location feature is used
- [ ] App requests microphone permission only when audio feature is used
- [ ] App requests storage/photo permission only when needed
- [ ] App handles permission denied gracefully (shows explanation, doesn't crash)
- [ ] App prompts user to enable permission from settings if permanently denied
- [ ] App does not access device resources without explicit permission

---

## 10. 🔁 App Lifecycle

- [ ] App state is preserved when backgrounded (e.g., form data not lost)
- [ ] App resumes correctly after being backgrounded
- [ ] App handles incoming phone calls during use gracefully
- [ ] App resumes correctly after an incoming call ends
- [ ] App handles interruptions (alarms, notifications) without crashing
- [ ] App correctly handles low memory warnings (does not crash)
- [ ] Force-closing and reopening the app restores appropriate state
- [ ] App handles device sleep/wake correctly

---

## 11. Accessibility

- [ ] VoiceOver (iOS) / TalkBack (Android) reads all interactive elements
- [ ] All images have descriptive alt text / content descriptions
- [ ] Buttons have descriptive labels (not just "button" or "icon")
- [ ] Minimum text size is at least 12sp/pt
- [ ] Dynamic text size (Accessibility font scaling) does not break layout
- [ ] Colour is not the only way to convey information
- [ ] Touch targets are at least 44x44pt (iOS) / 48x48dp (Android)

---

## 12. 🌍 Localisation (if applicable)

- [ ] All user-facing strings are translated correctly
- [ ] RTL (right-to-left) layout is correct for Arabic/Hebrew locales
- [ ] Date formats match locale (DD/MM/YYYY vs MM/DD/YYYY)
- [ ] Currency symbols and number formats are locale-appropriate
- [ ] No truncated translated text (some languages are longer)
- [ ] App name is correctly translated in target locales

---

## 13. 📱 Device Compatibility

Test on a minimum of the following:

### Android
- [ ] Latest Android version (Android 14+)
- [ ] Android 12 / 13
- [ ] Android 11 (older device support)
- [ ] Small screen (5–5.5 inch)
- [ ] Large screen (6.5 inch+)
- [ ] Tablet (if app supports tablets)

### iOS
- [ ] Latest iOS version (iOS 17+)
- [ ] iOS 16
- [ ] iOS 15 (if in support range)
- [ ] iPhone SE (small screen)
- [ ] iPhone 14/15 (standard)
- [ ] iPhone 14/15 Pro Max (large screen)
- [ ] iPad (if app supports iPad)

---

## 14. 🔄 Update & Version Testing

- [ ] App updates correctly from previous version
- [ ] Existing user data is preserved after update
- [ ] New features in the update are accessible
- [ ] No regression in existing features after update
- [ ] App does not require cache clear after update

---

## 15. 🔐 Security

- [ ] Sensitive data (passwords, tokens) is not stored in plain text
- [ ] App data is not accessible via device backup (for sensitive apps)
- [ ] SSL/TLS is enforced — app rejects HTTP connections
- [ ] Certificate pinning is implemented and working (where applicable)
- [ ] App does not log sensitive data (passwords, tokens) to console
- [ ] Session tokens are stored securely (Keychain/Keystore, not SharedPreferences)
- [ ] Screen content is hidden in app switcher for sensitive screens

---

*Checklist by Dipali Pagire | QA Engineer | Pune, India*
