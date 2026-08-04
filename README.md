# iOS+macOS 27 Specialist

A shared plugin for Codex and Claude Code containing seven skills for modern Apple-platform development.

## Included skills

- `adopt-c-bounds-safety` — adopt and debug the C `-fbounds-safety` extension
- `audit-xcode-security-settings` — review and harden Xcode build settings
- `device-interaction` — verify apps through screenshots, UI hierarchy, and touch interaction
- `modernize-tests` — migrate XCTest suites to Swift Testing
- `swiftui-specialist` — apply current SwiftUI patterns and performance guidance
- `swiftui-whats-new-27` — use SwiftUI APIs and migrations introduced with the 2027 OS releases
- `uikit-app-modernization` — modernize UIKit lifecycle, screen, orientation, and safe-area handling

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
