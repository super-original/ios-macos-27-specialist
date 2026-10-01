# iOS+macOS 27 Specialist

A shared plugin for Codex and Claude Code containing fifteen skills for modern Apple-platform development.

## Included skills

- `accessibility-dynamic-type-specialist` — audit text scaling and layouts at accessibility sizes
- `accessibility-sufficient-contrast-specialist` — audit text and UI contrast
- `accessibility-voiceover-specialist` — audit labels, traits, and screen-reader navigation
- `adopt-c-bounds-safety` — adopt and debug the C `-fbounds-safety` extension
- `app-intents-specialist` — apply App Intents best practices and correctness guidance
- `app-intents-whats-new-27` — adopt App Intents APIs introduced in iOS 26/27 and aligned releases
- `app-resizability` — prepare UIKit and SwiftUI apps for resizing, multiple windows, and iPhone Duo
- `audit-xcode-security-settings` — review and harden Xcode build settings
- `building-document-based-swiftui-applications` — build and migrate SwiftUI document apps
- `device-interaction` — verify apps through screenshots, UI hierarchy, and touch interaction
- `modernize-tests` — migrate XCTest suites to Swift Testing
- `swiftui-specialist` — apply current SwiftUI patterns and performance guidance
- `swiftui-whats-new-27` — use SwiftUI APIs and migrations introduced with SDK 27 and later
- `translation` — translate String Catalog entries with locale-specific style guides
- `translation-coordinator` — prepare and coordinate project localization

## Install in Codex

```bash
codex plugin marketplace add super-original/ios-macos-27-specialist --ref main
codex plugin add ios-macos-27-specialist@super-original
```

Start a new Codex task after installation so the skills are loaded.

## Install in Claude Code

```bash
claude plugin marketplace add super-original/ios-macos-27-specialist
claude plugin install ios-macos-27-specialist@super-original
```

Run `/reload-plugins` in Claude Code if the installer asks you to activate the plugin in the current session.

## Repository layout

- `.agents/plugins/marketplace.json` — Codex marketplace
- `.claude-plugin/marketplace.json` — Claude Code marketplace
- `plugins/ios-macos-27-specialist/.codex-plugin/plugin.json` — Codex manifest
- `plugins/ios-macos-27-specialist/.claude-plugin/plugin.json` — Claude Code manifest
- `plugins/ios-macos-27-specialist/assets/icon.png` — Codex plugin icon
- `plugins/ios-macos-27-specialist/skills/` — shared skill source

## Source and update status

Version **0.2.0** includes all **15 skills** and their supporting resources from the complete integration plugin packaged with **Xcode 27.1 beta (27A9269)**, exported on **2026-10-01**. The standalone `agent skills export` command returns only ten; the complete plugin also contains three accessibility skills and two translation skills, including 56 locale style guides.

Apple’s expanded `app-resizability` skill replaces `uikit-app-modernization`. It adds explicit iPhone Duo and resizing workflows, SwiftUI guidance, idiom modernization, and updated orientation and safe-area handling. See Apple’s [Prepare your app for iPhone Duo](https://developer.apple.com/videos/play/tech-talks/111461/) walkthrough. This release also includes the App Intents and document-app skills, security and device updates, and SwiftUI guidance introduced since this repository’s original export.

Apple’s skill bodies and supporting resources are imported without editorial corrections. The only import adaptations are compatible skill frontmatter and discovery descriptions, plus translation skill references renamed from `xcode-integration:` to this plugin’s `ios-macos-27-specialist:` namespace. Any issues found in Apple’s guidance are review findings, not changes to the imported content.

The skill inventory is verified against **27.1 beta**, not 27.2 beta. Apple’s [Xcode 27.2 release notes](https://developer.apple.com/documentation/xcode-release-notes/xcode-27_2-release-notes) direct developers to Xcode 27.1 for iPhone Duo SDK and simulator support.

To check a future Xcode release, export into a separate directory, then compare it with `plugins/ios-macos-27-specialist/skills/`:

```bash
xcodebuild -version
xcrun agent skills export /tmp/ios-macos-27-skills-review
xcrun agent plugin path --plugin-format codex
```

Compare the `skills/` directory returned by the plugin command as well: the standalone export can omit bundled skills.

The translation skills require Xcode’s `LocalizationPlanner`, `StringCatalogRead`, `StringCatalogContext`, and `StringCatalogEdit` tools; the coordinator also requires sub-agent support. Device interaction requires Xcode’s device tools. This repository supplies the skills, not those tool connections. The accessibility skills also reference Xcode file-reading and preview workflows.

Preserve Apple’s guidance when incorporating upstream changes; limit adaptations to plugin compatibility and internal skill references. Keep both plugin manifest versions in sync.
