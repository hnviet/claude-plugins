# hnviet's Claude Plugins Marketplace

A personal marketplace of Claude plugins for Cowork, Claude Desktop, and Claude Code. It can hold many plugins; each lives in `plugins/<name>/` and is listed in `.claude-plugin/marketplace.json`.

## Plugins

**aitinkerers** connects Claude to your AI Tinkerers organizer account (events, RSVPs, screening, speakers, sponsors, promo, analytics). It is a community connector where you bring your own key, and it is not officially affiliated with AI Tinkerers.

## Install

In Claude, run `/plugin marketplace add hnviet/claude-plugins`, then `/plugin install aitinkerers@hnviet-plugins`. After installing, set your own AI Tinkerers key as described in `plugins/aitinkerers/README.md` (recommended: the environment variable `AITINKERERS_API_KEY`).

## Security

No keys are stored in this repo. Each user supplies their own AI Tinkerers agent key and controls only their own account.
