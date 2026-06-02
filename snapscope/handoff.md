# SnapScope Handoff

## Product Summary

SnapScope is an iPhone-only, offline SwiftUI field report app. It helps users create local projects, add evidence notes, classify severity/status, and export a PDF report. The app is designed for overseas App Store release with English and Simplified Chinese localization.

## Key App Facts

- App name: SnapScope
- Chinese display name: 现场记
- Bundle ID: `com.zhouyajie.snapscope`
- Version: `1.0.0`
- Build number: `1`
- Support email: `jay212315@gmail.com`
- Data model: local JSON files plus optional generated PDF exports under app documents.
- Backend/account/network: none.

## Important Paths

- Xcode project: `SnapScope.xcodeproj`
- App entry: `SnapScope/App/SnapScopeApp.swift`
- Models: `SnapScope/Models/FieldReportModels.swift`
- Local storage: `SnapScope/Services/ReportStore.swift`
- PDF export: `SnapScope/Services/PDFReportRenderer.swift`
- Localization helper: `SnapScope/App/AppLocale.swift`
- Main UI: `SnapScope/Views/ContentView.swift`
- Settings: `SnapScope/Views/SettingsView.swift`
- App Store metadata: `docs/app-store-connect-template.md`
- Web privacy/support pages: `docs/privacy.html`, `docs/support.html`
- Screenshot script: `scripts/capture_app_store_screenshots.sh`
- Icon script: `scripts/generate_icon.swift`
- GitHub retry script: `scripts/setup_github_repo.py`
- GitHub Pages workflow: `.github/workflows/pages.yml`

## Build And Screenshot Commands

```bash
xcodebuild -project SnapScope.xcodeproj -scheme SnapScope -configuration Debug -destination 'platform=iOS Simulator,name=iPhone 17 Pro Max' build
./scripts/capture_app_store_screenshots.sh
```

## Verified State

- Debug simulator build passed on Xcode 26.2.
- Generated 6.5-inch screenshots are 1284x2778.
- Icon is 1024x1024 and has no alpha channel.
- No third-party SDKs are present.
- App code has no `URLSession`, analytics, ads, account, or backend implementation.
- The only web URLs are user-initiated Settings links to support/privacy pages.
- Local Git repository has an initial app commit and a GitHub Pages handoff commit; use `git log --oneline` for the current hashes.
- GitHub repository creation was attempted but blocked by token permissions (`403 Resource not accessible by personal access token`).

## Localization Notes

The app includes `en.lproj` and `zh-Hans.lproj`. Runtime copy uses `String(localized:)` and a small helper that defaults China region users to Simplified Chinese, with English fallback elsewhere. `InfoPlist.strings` localizes `CFBundleDisplayName`.

## Known Manual Follow-Up

- Confirm Apple Developer Team ID and signing profile in Xcode.
- Create the App Store Connect app record manually if automatic creation is not desired.
- Create or retry creation of `Davidzyj/snapscope`, push `main`, and enable GitHub Pages with GitHub Actions as source.
- Verify final GitHub Pages URL after repository creation. Expected URL: `https://Davidzyj.github.io/snapscope/`.
- Add real App Store screenshots from `AppStoreScreenshots/` in App Store Connect.
