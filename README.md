# Victor

I build iPhone apps and the small tools that make shipping them less painful, and I fix bugs in the open-source projects I depend on.

## Tools I maintain

**[limitbar](https://github.com/vsolano9/limitbar)** (v2.1.0). A Windows 11 taskbar widget that shows how much of your AI plan limits you have used: Claude Code, Codex, Grok and Cursor out of the box, plus any HTTP endpoint, script or file you point it at. One 0.6 MB native Rust exe, read-only with your existing sign-ins.

**App Store submission preflight.** Four separate CLIs that check a [fastlane `deliver`](https://docs.fastlane.tools/actions/deliver/) tree, or the app sources behind it, before App Store Connect sees it. The three Node tools have no runtime dependencies, run offline and exit non-zero, so they can gate CI.

| Tool | What it checks | Install |
| --- | --- | --- |
| [metaproof](https://github.com/vsolano9/metaproof) | Localized metadata text: required files, field lengths, the ASO keyword field, URLs. Safe `--fix` for keyword separators and duplicates. | npm `metaproof@0.6.1`, Action `vsolano9/metaproof@v0.6.1` |
| [screenproof](https://github.com/vsolano9/screenproof) | Screenshot and app-preview files: dimensions, format, counts, locale folders, video codec, duration and audio. | npm `screenproof@0.7.0`, Action `vsolano9/screenproof@v0.7.0` |
| [localeproof](https://github.com/vsolano9/localeproof) | Locales the app ships (`*.xcstrings`, `knownRegions`, `*.lproj`) against the locales the listing promises. | npm `localeproof@0.1.0`, Action `vsolano9/localeproof@v0.1.0` |
| [claimproof](https://github.com/vsolano9/claimproof) | What the screenshots say: Vision OCR read back and compared with String Catalogs, `.strings`, Swift literals and your real price. macOS only. | Clone and build with `swiftc` (v0.1.1) |

Also public: [agent-grid](https://github.com/vsolano9/agent-grid) (a macOS app with Codex, Claude, Grok and Cursor Agent terminals in one grid), [splat-walk](https://github.com/vsolano9/splat-walk) (a three.js WebGPU Gaussian splat explorer) and [voice-rewriter](https://github.com/vsolano9/voice-rewriter) (`voice-rewriter@0.1.1`, a fail-closed Gemini rewriter that rejects drafts whose facts or meaning drift).

## Upstream work

99 merged pull requests in 38 repositories so far (October 2026). Mostly bug fixes and the tests that pin them. A few I like:

- [open-policy-agent/opa #8946](https://github.com/open-policy-agent/opa/pull/8946): `opa test --format json` results can be read back into structured errors.
- [goss-org/goss #1099](https://github.com/goss-org/goss/pull/1099): fixed a nil-pointer panic in `AndMatcher` that had been open for 23 months, plus four follow-ups ([#1096](https://github.com/goss-org/goss/pull/1096), [#1097](https://github.com/goss-org/goss/pull/1097), [#1098](https://github.com/goss-org/goss/pull/1098), [#1107](https://github.com/goss-org/goss/pull/1107)).
- [carvel-dev/ytt #1000](https://github.com/carvel-dev/ytt/pull/1000): files saved with a UTF-8 BOM now parse in YAML, Starlark and text templates.
- [ClickHouse/clickhouse-connect #995](https://github.com/ClickHouse/clickhouse-connect/pull/995): a failed Cython build now stops instead of silently installing the slow pure-Python fallback.
- [dynamodb-toolbox #1260](https://github.com/dynamodb-toolbox/dynamodb-toolbox/pull/1260): `castAs<T>()` types survive `updateLink` callbacks.
- [nodejs/doc-kit #933](https://github.com/nodejs/doc-kit/pull/933), [SUSE/connect-ng #429](https://github.com/SUSE/connect-ng/pull/429), [getsentry/MobileBuildMCP #456](https://github.com/getsentry/MobileBuildMCP/pull/456), and three fixes each to [sqlfmt](https://github.com/tconbeer/sqlfmt/pulls?q=is%3Apr+author%3Avsolano9+is%3Amerged), [MyIP](https://github.com/jason5ng32/MyIP/pulls?q=is%3Apr+author%3Avsolano9+is%3Amerged) and [MacSai](https://github.com/iliyami/MacSai/pulls?q=is%3Apr+author%3Avsolano9+is%3Amerged).
- [jocosocial/swiftarr](https://github.com/jocosocial/swiftarr/pulls?q=is%3Apr+author%3Avsolano9+is%3Amerged): 11 merged, including CI that now runs the 59 database-backed tests that had never executed.

I use AI coding agents (Claude Code and Codex) for much of this work.

Site: [thechosenvictor.com](https://www.thechosenvictor.com/)
