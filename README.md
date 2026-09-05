# scoop-svipall

A [Scoop](https://scoop.sh) bucket for [Svipall](https://github.com/ilien-dev/svipall): local-first
web scraping and captcha MCP server for AI agents.

```powershell
scoop bucket add svipall https://github.com/ilien-dev/scoop-svipall
scoop install svipall
```

Windows x86-64. It installs the release build, checked against the `sha256sums.txt` published with
that release, and puts `svipall` and `svipall-mcp` on your PATH.

Then:

```powershell
svipall doctor                          # what this installation can do, and how to fix what it cannot
claude mcp add svipall -- svipall-mcp   # wire it into Claude Code
```

Browser tiers need a Chromium-based browser. Microsoft Edge ships with Windows and already counts;
`svipall browser install` fetches a Chrome for Testing of its own, about 190 MB.

## How this bucket is updated

`bucket/svipall.json` is generated, not hand-written. It is rendered from the release's own
`sha256sums.txt` by [`scripts/render-packaging.sh`](https://github.com/ilien-dev/svipall/blob/main/scripts/render-packaging.sh)
in the main repository, so no checksum is ever typed twice. The template lives at
`packaging/templates/scoop.json` there. The manifest carries `checkver` and `autoupdate`, so later
version bumps can also come from Scoop's own excavator.

Issues and pull requests belong in [ilien-dev/svipall](https://github.com/ilien-dev/svipall), not
here.

## Licence

Svipall is AGPL-3.0-only. This bucket carries only packaging metadata.
