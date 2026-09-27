# Pebbo Agent Plugins

Agent plugins for the Pebbo marketplace, version 1.1.0.

MCP endpoint: https://paeagnzrcnxkkmotwdue.supabase.co/functions/v1/mcp

Search and inspect public Pebbo listings, see who posted a listing and a user's listings by username, see a seller's other listings, browse the latest listings, the listings in your community and those near the location you saved in Pebbo, and read your own and your liked listings. Nearby results use only the location you saved in the Pebbo app, with the same center and 25 km radius as the app's Nearby tab, and only when the app is set to use that saved location for Nearby; never your device's location. The agent is not sent that location, but from the order of nearby listings it can work out closely where it is, and community listings show your community. The agent sees other people by display name and @username, never by their email. Requires a Pebbo account: the client asks you to sign in on first use. Search can return sold listings; currency is unspecified. Liking and publishing each need their own approval. With publishing approved, the agent can post, edit, mark sold and delete your own listings, and give you a link to add photos yourself; it never receives the photos. Messaging and purchases are not supported.

Website: https://pebbo.app. Privacy policy: https://pebbo.app/privacy. Terms: https://pebbo.app/terms.

## Install

This repository is a plugin marketplace named `pebbo`.

Claude Code: run `/plugin marketplace add xysoft-dev/pebbo-plugins`, then `/plugin install pebbo-claude@pebbo`, and start a new session.

Codex: run `codex plugin marketplace add xysoft-dev/pebbo-plugins`, then `codex plugin add pebbo-openai@pebbo` or install Pebbo from the plugin directory, and start a new task. If Codex reports that the pebbo MCP server is not logged in, run `codex mcp login pebbo`.

Each release is tagged `v<version>`. To stay on this release instead of following the latest, add `xysoft-dev/pebbo-plugins#v1.1.0` in Claude Code or `xysoft-dev/pebbo-plugins@v1.1.0` in Codex.

If an earlier Pebbo plugin is installed, disable it and start a new session. Every version shares one plugin name, skill name and MCP server, so leaving two enabled makes it unclear which one answered.

## Update, Verify And Roll Back

To update in Claude Code, run `/plugin marketplace update pebbo` in a session, or from a terminal run `claude plugin marketplace update pebbo` and then `claude plugin update pebbo-claude@pebbo`; then restart. Claude Code does not update this marketplace on its own unless you turn on auto-update for `pebbo` under Marketplaces in `/plugin`. In Codex, run `codex plugin marketplace upgrade pebbo` and then `codex plugin add pebbo-openai@pebbo`, and start a new task.

Ask the agent to find a bicycle on Pebbo, inspect a returned listing, and open its canonical link. Links open the Pebbo app or its download fallback. Never paste credentials into these files.

`release.json` records the package version, source revision and SHA-256 checksums of every file. The source revision identifies a commit in Pebbo's private source repository and is not fetchable by consumers; it is provenance metadata only.

To roll back, remove the `pebbo` marketplace, add it again pinned to the earlier release's tag as above, and reinstall. Package rollback is independent of the Pebbo service: it does not change the server the endpoint points to.

## Disconnect

Removing or disabling the plugin does not end the access you approved. To end it, open https://pebbo.app/oauth/consent/ in your browser, sign in with the same Pebbo account, and press Disconnect next to the app.

## License

Copyright 2026 XYSOFT LLC. Licensed under the Apache License, Version 2.0. See `LICENSE`. Pebbo is a trademark of XYSOFT LLC.
