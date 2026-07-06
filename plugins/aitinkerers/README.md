# AI Tinkerers connector

Connect Claude (Cowork, Claude Desktop, or Claude Code) to your **AI Tinkerers** organizer account — events, RSVPs, screening, speakers, sponsors, promo, and analytics.

## Bring your own key

This connector does **not** include a key. Each person uses their **own** AI Tinkerers agent key, so Claude only ever acts on your account. Get yours at **https://aitinkerers.org/developers** (it looks like `sk_...`).

Give the connector your key one of two ways:

### Option A — environment variable (recommended)
Set an environment variable `AITINKERERS_API_KEY`, then fully restart Claude:
- **Windows (PowerShell):** `setx AITINKERERS_API_KEY "sk_your_key"`
- **macOS / Linux:** add `export AITINKERERS_API_KEY=sk_your_key` to `~/.zshrc` or `~/.bashrc`

The connector reads `${AITINKERERS_API_KEY}` at runtime, so it survives plugin updates and never writes your key to a file.

### Option B — edit the installed .mcp.json
Paste the key into the copy Claude actually runs — NOT the `plugins/marketplaces/...` clone (editing that has no effect):
1. Open `installed_plugins.json` in your Claude plugins folder (Windows: `C:\Users\<you>\.claude\plugins\installed_plugins.json`; macOS/Linux: `~/.claude/plugins/installed_plugins.json`).
2. Find the `aitinkerers@hnviet-plugins` entry and copy its `installPath` (e.g. `.../plugins/cache/hnviet-plugins/aitinkerers/0.1.0`).
3. Open `.mcp.json` in that `installPath` and change the Authorization line: replace `${AITINKERERS_API_KEY}` with your real key, e.g. `Bearer sk_your_key`.
4. Fully quit Claude / Cowork from the system tray and reopen. Do not click "Connect" — a valid key connects automatically.
5. Note: `installPath` is version-specific, so a plugin update means redoing this — which is why Option A is sturdier.

## Security
Your agent key controls your AI Tinkerers account — treat it like a password. Prefer Option A; if you use Option B, keep the file local and never commit a key. Rotate anytime at https://aitinkerers.org/developers.

## What Claude can do once connected
Events & meetups, RSVP management and screening, speaker proposals & pipeline, sponsor search & outreach, subscriber/email analytics, message board, promo banners & social posts, and organizer docs.
