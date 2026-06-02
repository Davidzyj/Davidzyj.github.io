# SnapScope Product Plan

## Positioning

SnapScope is an offline iPhone tool for contractors, property managers, cleaners, inspectors, and small service teams who need to turn job photos into clear local reports without accounts or cloud storage.

## Core User Promise

Create a job, attach or capture evidence-style notes, mark severity, and export a clean report from data that stays on the device.

## MVP Scope

- iPhone-only SwiftUI app.
- Local project and photo-note records saved on device.
- Bilingual English and Simplified Chinese interface.
- Region-based default language: China uses Simplified Chinese, other regions use English, while still respecting iOS localization.
- Demo data only when launched for screenshot automation.
- Settings page with privacy/support links and no user-facing Bundle ID.
- PDF report export through the system share sheet.
- No account, no backend, no analytics, no ads, no tracking, and no app-initiated network request.

## Target App Store Category

Primary: Productivity

Secondary candidate: Utilities

## First Release Risks

- Camera capture is intentionally not requested automatically to avoid first-run permission prompts in screenshots. Users can create notes manually in 1.0.0; photo-library/camera capture can be added after manual device testing.
- PDF export is local and system-share based; users must choose where to send or save the report.
- GitHub Pages URLs depend on the final GitHub repository owner/name after remote creation.

