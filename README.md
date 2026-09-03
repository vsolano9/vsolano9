# Victor

I build iPhone apps and small tools for the boring parts of shipping.

## Submission-preflight suite

These tools check a [fastlane `deliver`](https://docs.fastlane.tools/actions/deliver/) tree (or the matching app sources) **before** App Store Connect sees it. Each one is a separate repo. They do not call each other.

| Tool | What it checks | Install |
| --- | --- | --- |
| [metaproof](https://github.com/vsolano9/metaproof) | Localized metadata text: required files, field length, ASO keyword field, URLs. Safe `--fix` for keyword separators and duplicates. | npm `metaproof@0.6.1`, Action `vsolano9/metaproof@v0.6.1` |
| [screenproof](https://github.com/vsolano9/screenproof) | Screenshot and app-preview files: dimensions, format, counts, locale folders, video codec/duration/audio. | npm `screenproof@0.5.2`, Action `vsolano9/screenproof@v0.5.2` |
| [localeproof](https://github.com/vsolano9/localeproof) | Locales the iOS app ships (`*.xcstrings`, `knownRegions`, `*.lproj`) versus locales the listing promises (`metadata/`, `screenshots/`). | npm `localeproof@0.1.0`, Action `vsolano9/localeproof@v0.1.0` |
| [claimproof](https://github.com/vsolano9/claimproof) | What the screenshots **say**: Vision OCR versus String Catalogs, `.strings`, Swift literals, and an explicit `--price`. macOS only. | Clone + `swiftc`; not on npm |

The three Node tools are zero runtime dependencies, offline, and exit non-zero so they can gate CI. `claimproof` is Python 3.10+ plus a compiled `ocr.swift` helper (Apple Vision). No credentials.

## Other public tools

[voice-rewriter](https://github.com/vsolano9/voice-rewriter) (`voice-rewriter@0.1.1`) rewrites a post or reply from a user-supplied voice profile using Gemini (`gemini-flash-latest`, high reasoning). It fails closed on factual or meaning drift. It needs `GEMINI_API_KEY`. It does not research facts.

## This repository

`vsolano9/vsolano9` is only the GitHub profile README. It is not a library and has no install step.

## Contribution

First merged contribution: [getsentry/XcodeBuildMCP #456][xcodebuildmcp-456], test coverage for SwiftUI tab identifier surfacing. Merged July 2026.

[xcodebuildmcp-456]: https://github.com/getsentry/XcodeBuildMCP/pull/456

Site: [thechosenvictor.com](https://www.thechosenvictor.com/)
