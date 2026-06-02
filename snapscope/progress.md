# SnapScope Progress Log

## 2026-06-01

- Chose product direction: offline field photo report tool for iPhone users.
- Set product name to SnapScope and Bundle ID to `com.zhouyajie.snapscope`.
- Started native SwiftUI project from an empty workspace.
- Planned bilingual app, bilingual GitHub Pages support/privacy site, local-only storage, 1.0.0 release metadata, App Store screenshots, and handoff documentation.
- Created native SwiftUI iPhone-only Xcode project.
- Implemented local JSON persistence for reports and evidence notes.
- Implemented PDF export through the iOS share sheet.
- Added English and Simplified Chinese app localization, including localized `CFBundleDisplayName`.
- Added Settings page with support, privacy, and support email links; Bundle ID is not shown to users.
- Added bilingual GitHub Pages website pages: home, privacy policy, and support.
- Generated a designed 1024x1024 App Store icon with no alpha channel.
- Generated English and Simplified Chinese 6.5-inch App Store screenshots from the real running simulator app.
- Verified screenshot dimensions: all generated screenshots are 1284x2778.
- Verified Debug simulator build succeeds with Xcode 26.2.
- Prepared App Store Connect metadata, privacy answers, review notes, and handoff documentation.
- Initialized local Git repository and committed the project.
- Attempted to create `Davidzyj/snapscope` via GitHub API; blocked because the available token returned `403 Resource not accessible by personal access token`.
- Added a GitHub Pages workflow and `scripts/setup_github_repo.py` so repository creation/push can be retried after granting token permissions or after manual repository creation.
- Added final handoff notes for GitHub Pages deployment.
- Renamed Simplified Chinese display name and listing copy to `现场记`.

## Verification Commands

```bash
plutil -lint SnapScope/Resources/Info.plist
plutil -lint SnapScope/Resources/en.lproj/Localizable.strings
plutil -lint SnapScope/Resources/zh-Hans.lproj/Localizable.strings
xcodebuild -project SnapScope.xcodeproj -scheme SnapScope -configuration Debug -destination 'platform=iOS Simulator,name=iPhone 17 Pro Max' CODE_SIGNING_ALLOWED=NO build
./scripts/capture_app_store_screenshots.sh
```

## Generated Assets

- App icon: `SnapScope/Resources/Assets.xcassets/AppIcon.appiconset/AppIcon-1024.png`
- English screenshots: `AppStoreScreenshots/en/`
- Simplified Chinese screenshots: `AppStoreScreenshots/zh-Hans/`
- Screenshot contact sheet: `AppStoreScreenshots/previews/contact-sheet.jpg`

## GitHub Pages Follow-Up

The static site is ready under `docs/`, and `.github/workflows/pages.yml` deploys it through GitHub Pages Actions after the repository exists.

Current blocker: the available GitHub token cannot create repositories. Retry with a token that has repository creation/push permissions:

```bash
GITHUB_PAT_TOKEN=... scripts/setup_github_repo.py
```
