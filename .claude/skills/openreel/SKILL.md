---
name: openreel
description: Set up and use OpenReel Video (open-source video editor, openreel.video) with Claude through its desktop MCP server. Use when the owner wants Claude to edit a video in OpenReel - cut clips, add captions/text, mix audio, export - or asks how to connect OpenReel to Claude.
---

# OpenReel Video + Claude

OpenReel Video (https://github.com/Augani/openreel-video, MIT) is a browser and desktop video
editor. Only the **desktop app** exposes an MCP server, and it listens on `127.0.0.1` of the
owner's computer. So Claude must run **on that same computer** (Claude Code CLI or Claude
Desktop). A cloud session (claude.ai/code) cannot reach it.

## Setup (on the owner's computer, once)
1. Install the desktop app from https://github.com/Augani/openreel-video/releases/latest
   (macOS dmg, Windows installer, Linux `.deb` or AppImage). On Linux prefer `.deb`: an AppImage
   mounts under a new `/tmp/.mount_*` path each launch, which breaks the saved MCP path.
2. Node.js must be installed (`node -v`): the bridge `openreel-mcp` is a Node script.
3. Start OpenReel, open **Settings -> MCP**. It shows the local URL, a bearer token and a ready
   client snippet with the full path to `openreel-mcp`. The bridge reads the URL and token from
   the endpoint file the running app writes, so the token is never pasted anywhere.
4. Add it to Claude:
   - Claude Code: `claude mcp add openreel -- node "<path to openreel-mcp from step 3>"`
   - Claude Desktop: paste the snippet into `claude_desktop_config.json`, restart the app.
5. In Settings -> MCP press **Test connection**. Then in Claude run `/mcp` (Claude Code) and
   check `openreel` is connected.

OpenReel must be running with a project open whenever Claude edits; if the tools fail, check
that first.

## Working rules
- Delete, remove and export calls are refused over MCP with "confirmation required" unless the
  owner turned on **Trusted local - auto-allow**. Leave it off; ask the owner before any
  delete/export and let them confirm in the app.
- Every turn is one undoable transaction; tell the owner they can undo a whole turn in the app.
- About 228 tools cover import, timeline, trim, crop, transform, color, audio, text, subtitles,
  keyframes, transitions, motion compositions and export. Full list:
  https://github.com/Augani/openreel-video/blob/main/docs/AGENT-CAPABILITIES.md
- Before editing, read the project state (tracks, clips, durations), then describe the plan in
  one or two lines, then apply it. After applying, read the state again and report what changed.
- For the owner's short vertical ads (TikTok / Reels / Shorts): 1080x1920, captions on, first
  2 seconds carry the hook, keep claims truthful (no invented reviews, prices or guarantees).
