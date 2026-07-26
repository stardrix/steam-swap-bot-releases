# Steam Swap Bot

[![Latest Release](https://img.shields.io/github/v/release/stardrix/steam-swap-bot-releases?label=Latest%20Release&style=for-the-badge&color=a855f7)](https://github.com/stardrix/steam-swap-bot-releases/releases/latest)

> The easiest **Steam swap bot for a level up profile**. An automated **1:1 same-set trading card exchange** running 24/7 on your own account — traders give a duplicate card and receive a card they are missing from the same set. No keys, no gems, no currency. Fully integrated with the #1 **Steam bot listing** directory.

**[Get a license](https://www.steamtradebots.com/) · [Join Discord](https://discord.gg/XCtgnPsZFU) · [Report an issue](https://github.com/stardrix/steam-swap-bot-releases/issues)**

---

## Overview

Steam Swap Bot is a Windows / Linux desktop application built on Electron. It runs a **1:1 same-set card swap service** (the SteamTrade Matcher / STM model) on your Steam account: traders browse your bot's inventory, offer a card they have spare, and take a card they still need from the same game. The bot checks every offer against strict swap rules and accepts it automatically within seconds.

Swap bots are the simplest kind of card bot to run — there is no pricing to manage, no keys or gems to stock, and no rates to keep competitive. Your inventory does the work.

### What it swaps

| Item | Swaps |
|---|---|
| Normal trading cards | ✅ 1:1 within the same game |
| Foil trading cards | ✅ 1:1 within the same game (foil ↔ foil only) |
| Cards across different games | ❌ Never — same set only |
| Foil ↔ normal | ❌ Never — a foil card cannot complete a normal badge |
| Gems, emoticons, backgrounds, booster packs | ❌ Rejected on both sides |
| Keys, currency, items from other games | ❌ Rejected on both sides |

---

## 🌐 The SteamTradeBots Ecosystem

To get the most out of your bot and build trust with your users, take advantage of our full ecosystem:

- **📈 Get Traffic (Bot Directory):** Don't just run a bot get customers! Submit your account to our official **[Steam Bot Listing](https://www.steamtradebots.com/)** to display your live card stock to thousands of users looking to complete their sets.
- **🛡️ Build Trust (Chrome Extension):** Tell your customers to install the **[SteamTradeBots Verified Extension](https://chromewebstore.google.com/detail/steamtradebots-verified-b/ifbjmpaibhdfjemngaajlmijgopcaopk)**. It places a green "Verified Bot" banner directly on your bot's Steam profile, proving your legitimacy and protecting your users from impersonation scams.

---

## Key Features

- **Fully automatic 1:1 swapping**:
traders send their own offers and the bot validates and accepts them within seconds — no input from you

- **Strict same-set enforcement**:
every offer is checked per set, so a card from one game can never be swapped for a card from another, and foil is never swapped for normal

- **Scam-proof offer validation**:
equal card counts, cards only, no same-card swaps, and a configurable size cap — anything that isn't a clean 1:1 same-set swap is declined with a clear explanation to the trader

- **Two swap modes**:
run in **Any** mode to accept every fair 1:1 swap (most popular with traders), or **Fair** mode to only swap when your bot gains a card it does not already own

- **Duplicate protection**:
optionally keep at least one of every card so the bot only ever trades away its spares

- **Matchmaking for traders**:
users can type `!check` to see every possible swap with your bot, or `!swap` to have the bot build and send the offer for them

- **Safe with concurrent traders**:
cards promised in a pending offer are reserved, so two traders are never offered the same card and nobody gets an "items no longer available" error

- **One active offer per trader**:
a trader who already has an open offer gets their existing offer link back instead of stacking duplicates — no offer spam

- **Steam rate-limit resilience**:
smart inventory caching, patient retries, and serialized mobile confirmations with shared backoff keep trades flowing even when Steam throttles busy IPs — built with VPS hosting in mind

- **Steam login-throttle handling**:
if Steam temporarily blocks logins (error 84 / 87), the dashboard shows a live countdown and explains that it is a Steam-side restriction, not a bot fault

- **One-click Support Report**:
a button in the Logs tab bundles version, OS, bot state, and recent logs (secrets always redacted) into a single report for fast support

- **Listing integration**:
your live card stock syncs automatically to the SteamTradeBots.com swap bot directory

- **Auto-update**:
new releases are downloaded and installed silently in the background

---

## How It Works

1. Install the app and activate your license
2. Add your Steam bot account credentials (username, password, shared secret, identity secret)
3. Choose your swap mode in the Swap Settings tab
4. Start the bot — it logs into Steam, loads your card inventory, and posts your listing
5. Traders browse your inventory, send a 1:1 same-set offer, and the bot accepts it automatically

Your bot's Steam inventory must be set to **Public** so traders can see the cards you offer.

---

## Dashboard

Live overview of the bot: status, total cards in stock, games covered, duplicates available to swap, completed swaps, and the swap rules currently in force.

<!-- SCREENSHOT PENDING — upload the image, then delete this comment wrapper to show it:
![Dashboard](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/Dashboard.png)
-->

---

## Bot Account

Configure your Steam credentials and access settings:

| Field | Description |
|---|---|
| Bot display name | Shown in the dashboard only |
| Steam Username | The bot account's login name |
| Steam Password | Account password (stored encrypted) |
| Steam Web API Key | Required for trade offer processing |
| Shared Secret | 2FA — the bot generates codes automatically |
| Identity Secret | Auto-confirms trades, no phone needed |
| Admin Steam IDs | These accounts bypass all swap rules |
| Owner Profile URL | Shown when users type `!OWNER` |

All secret fields are hidden behind a reveal toggle.

<!-- SCREENSHOT PENDING — upload the image, then delete this comment wrapper to show it:
![Bot Account](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/Bot%20Account.png)
-->

---

## Swap Settings

This is where you decide which swaps your bot accepts.

| Setting | Description |
|---|---|
| **Swap mode** | **Any** — accept every valid 1:1 same-set swap. **Fair** — only swap when the bot gains a card it does not already own. |
| **Keep one of each card** | Never give away the bot's last copy of a card, so it only trades duplicates |
| **Accept donations** | Auto-accept offers where somebody gives cards and asks for nothing back |
| **Auto-accept friend requests** | Traders must be friends to use chat commands |
| **Max cards per trade** | Size cap for a single offer (each side) |
| **Blocked games** | App IDs the bot will never trade |
| **Friend-list status text** | Custom "Now Playing" text with live values — `{cards}` `{games}` `{dupes}` `{normal}` `{foil}` `{mode}` |

Changes apply to the running bot instantly — no restart needed.

<!-- SCREENSHOT PENDING — upload the image, then delete this comment wrapper to show it:
![Swap Settings](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/Swap%20Settings.png)
-->

### Which mode should I run?

**Any** mode is what most successful swap bots use. Accepting every fair 1:1 swap makes your bot maximally useful, which is exactly what attracts repeat traders and keeps you visible in the listings. **Fair** mode is for operators who want to grow their own set collection — it protects diversity, but it turns away more traders.

---

## Swap Rules

Every incoming offer is checked before it is accepted. If anything fails, the offer is declined and the trader is told exactly why:

| Rule | Why |
|---|---|
| **Strictly 1:1** | Equal card counts on both sides |
| **Same set, counted per set** | The number of cards leaving a set must equal the number entering it — so "1 Dota card for 1 CS2 card" is rejected even though the totals match |
| **Foil and normal are separate sets** | A foil card cannot complete a normal badge, so cross-border swaps are rejected even within the same game |
| **Trading cards only** | Gems, emoticons, profile backgrounds, booster packs and items from other games are rejected on both sides |
| **No same-card swaps** | Swapping a card for the same card helps nobody |
| **Size cap** | Offers larger than your configured maximum are declined |
| **Last-copy protection** | With "keep one of each" enabled, an offer that would take the bot's final copy of a card is declined |

**Admins bypass every rule**, so you can stock or empty the bot freely from your own account.

---

## Listing

Connect your API key to the #1 verified **Steam bot listing** at SteamTradeBots.com. Your live card stock — total cards, games, duplicates and swap mode — is posted automatically and refreshed on a schedule you choose. Stopping the bot marks your listing offline so traders are never sent to a bot that isn't running.

<!-- SCREENSHOT PENDING — upload the image, then delete this comment wrapper to show it:
![Listing](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/Listing.png)
-->

---

## Swap History

Persistent log of every swap — accepted and declined — that survives restarts. Filter by **Today**, **7 Days**, **30 Days** or **All**. Each row shows the offer ID, the trading partner, how many cards moved each way, and the reason for any decline.

<!-- SCREENSHOT PENDING — upload the image, then delete this comment wrapper to show it:
![Swap History](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/Swap%20History.png)
-->

---

## Chat Commands

Traders interact with the bot directly over Steam chat.

| Command | Description |
|---|---|
| `!HELP` / `!COMMANDS` | List all available commands |
| `!CHECK` | Scan the trader's inventory and list every possible 1:1 swap with the bot |
| `!SWAP` | Build and send the trade offer automatically |
| `!STOCK` | Show the bot's current card stock |
| `!OWNER` | Show the owner's Steam profile link |
| `!IMABOT` | Confirms the account is a bot |

**Admin only:**

| Command | Description |
|---|---|
| `!ADMIN` | List admin commands |
| `!STATS` | Engine counters — swaps, cards moved, stock, uptime |
| `!REFRESH` | Force an inventory refresh |

> The trader's Steam inventory must be set to **Public** for `!CHECK` and `!SWAP` to work.

### How matching works

When a trader runs `!CHECK` or `!SWAP`, the bot compares both inventories set by set. A swap is only proposed when the trader gets a card they are **missing**, and gives one they have a **spare** of — so both sides come out ahead. Each missing card is offered only once, because a trader only needs one copy to complete a badge.

---

## Chat Monitor

Live feed of Steam chat messages and incoming trade offers, with each trader's Steam ID and the bot's response.

<!-- SCREENSHOT PENDING — upload the image, then delete this comment wrapper to show it:
![Chat Monitor](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/Chat%20Monitor.png)
-->

---

## Logs

Raw bot log output with INFO, WARN, and ERROR entries. One-click clear.

The **🛟 Support Report** button gathers everything support needs — app version, OS, bot state, and the recent log — into one report, copied to your clipboard and saved as a file. Passwords, secrets, and API keys are never included. If something goes wrong, send that one paste instead of screenshots.

<!-- SCREENSHOT PENDING — upload the image, then delete this comment wrapper to show it:
![Logs](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/Logs.png)
-->

---

## Getting a License

Visit **[steamtradebots.com](https://www.steamtradebots.com/)** to purchase and activate a license. The license is tied to your machine and validated on startup.

---

## Support & Community

Questions, bugs, or feature requests:

- **Discord:** [discord.gg/XCtgnPsZFU](https://discord.gg/XCtgnPsZFU)
- **Issues:** [github.com/stardrix/steam-swap-bot-releases/issues](https://github.com/stardrix/steam-swap-bot-releases/issues)
- **Email:** support@steamtradebots.com

---

## Running on a VPS

The bot works on datacenter/VPS hosting out of the box: inventory requests retry patiently through Steam's per-IP rate limits, recently fetched inventories are cached and reused, mobile confirmations are sent one at a time with a shared backoff, and background Steam traffic is kept to a minimum.

### Choosing a VPS provider

Steam rate-limits by IP address, and an IP's history matters: ranges belonging to popular budget hosts are shared with many other Steam bots, so they often arrive pre-throttled. For the smoothest experience we recommend a **premium VPS provider with a clean, dedicated IP** over the cheapest option — the few extra euros per month buy you an IP reputation that Steam treats far better.

Before committing to a provider (or after receiving a new IP), you can test it in seconds: open `https://steamcommunity.com/inventory/<your-bot-steamid64>/753/6` in a browser on the VPS. A JSON response means the IP is fine; an immediate error on the very first request means the IP range is throttled — ask your host for a different IP or pick another provider.

---

## Requirements

- Windows 10/11 (x64)
- Linux (x64)
- A Steam account dedicated to being the bot, with a **public inventory**
- Steam Web API Key ([get one here](https://steamcommunity.com/dev/apikey))
- Shared Secret and Identity Secret from your Steam authenticator (SteamDesktopAuthenticator or WinAuth)
- A valid Steam Swap Bot license

---

*This repository contains release builds only. New versions are detected and installed silently by the app via GitHub Releases.*
