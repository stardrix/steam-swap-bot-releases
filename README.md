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

- **Multi-bot support**:
run and manage multiple Steam accounts from one dashboard, each with its own credentials, swap settings, card stock and history

- **Bot Overview**:
live grid showing every bot's status, swaps completed, card stock and uptime at a glance; start or stop any bot directly from the grid, or use Start All / Stop All

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

![Dashboard](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/Dashborad.png)

---

## Multi-Bot Support

Run multiple Steam accounts from one dashboard. Each bot has its own credentials, swap settings, listing key, card stock and swap history — completely isolated from the others.

- Switch between bots with the **Active Bot** selector in the sidebar
- Add, rename or remove bots at any time from the **Bot Account** page
- The **Bot Overview** page shows every bot with live status, swaps, card stock and uptime
- Start or stop bots individually, or use **Start All** / **Stop All**

One bot going offline, hitting a Steam rate limit or being stopped has no effect on the others.

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

![Bot Account](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/BotAccount.png)

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

![Swap Settings](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/SwapSettings.png)

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

![Listing](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/Listing.png)

---

## Swap History

Persistent log of every swap — accepted and declined — that survives restarts. Filter by **Today**, **7 Days**, **30 Days** or **All**. Each row shows the offer ID, the trading partner, how many cards moved each way, and the reason for any decline.

![Swap History](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/SwapHistory.png)

---

## Chat Commands

Traders interact with the bot directly over Steam chat.

| Steam chat | Discord / Telegram | What it does | Needs |
|---|---|---|---|
| `!HELP` / `!COMMANDS` | `/help` | How swapping with me works | anyone |
| `!STOCK` | `/stock` | How many cards I hold and how many are spare | anyone |
| `!OWNER` | `/owner` | My owner Steam profile | anyone |
| `!IMABOT` | **Steam only** | Confirm I am an automated bot | anyone |
| `!CHECK` | `/check` | Find 1:1 swaps between us, without sending anything | SteamID |
| `!SWAP` | `/swap` | Send me the swap offer you just checked | linked |

**Needs:** `anyone` works with no identity at all. `SteamID` means the bot has to know which Steam
account you are, either because you linked one or because you passed it. `linked` means a verified
linked account, because the command sends a real trade offer and the bot will not aim one at an
unproven account.

The two spellings are the same command. With the Chat Bridge running the bot rewrites its own
replies as well, so a usage hint that reads `!CHECK` on Steam reads `/check` on Discord. A trader is never shown a command they cannot type.


**On Telegram with more than one bot, name the one you want:** `/stock bot:Low`, `/check bot:Low`.
Discord does not need this, because the channel already says which bot you are talking to. Telegram
has no channels, so the name goes on the command. It can sit anywhere in the line and is never
treated as an argument. A bot called "Gem Trader" also answers to `bot:gem-trader`. With only one
bot running you can leave it off entirely.
**Discord and Telegram only.** These are about the bridge itself, so they have no Steam chat

`/botlist` on Telegram shows every bot, whether it is online, and exactly what to type for each.
It is a Telegram command only: on Discord the channel already tells you which bot you are talking
to, so there is nothing to list.
spelling. A trader runs them in the bot's channel or in a direct message.

| Command | What it does |
|---|---|
| `/link <steamid> [tradeurl]` | Link your Steam account so you can swap |
| `/verify <code>` | Finish linking with the code I sent you on Steam |
| `/unlink` | Forget the Steam account linked here |
| `/whoami` | Show which Steam account is linked here |
| `/tradeurl <tradeurl>` | Set your trade URL so I can send you offers |

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

## Chat Bridge (Discord & Telegram)

Let your traders use the bot from **Discord** or **Telegram** instead of Steam chat. Trading still happens through normal Steam trade offers, only the conversation moves.

**Why you might want this.** Steam counts what your account *sends*. A bot that greets every new friend, answers every mistyped command and prints a long help list is producing a lot of outbound messages, and that is what gets an account flagged. The Chat Bridge gives traders a better place to talk, and quietens Steam chat right down.

**One Discord bot runs all of your bots.** These settings are app-wide, not per bot, so you only ever need a single token no matter how many bots you run.

### What traders can do without linking anything

`/stock` `/owner` `/help`

These need no setup from the trader at all. Anyone in your server can see what cards you hold.

### What needs a linked Steam account

`/check` needs to know which Steam account they are asking about. `/swap` needs it **verified**, because otherwise someone could point the bot at a stranger and have it send trade offers to people who never asked for them.

Linking is one command and one Steam message, once, forever.

---

## Setting up Discord

### 1. Create the application

1. Go to <https://discord.com/developers/applications> and click **New Application**. Name it whatever you like, this is what traders will see.
2. Open the **Bot** tab, click **Reset Token**, and copy it. Treat it like a password.
3. **Check that "Interactions Endpoint URL" on the General Information page is empty.** If anything is in that box, Discord sends commands there instead of to your bot and nothing will work. This is the single most common setup problem.

> You do **not** need to enable any Privileged Gateway Intents. The bot uses slash commands, which need none of them.

### 2. Invite it to your server

Start the card bot with the token saved, then open the **Logs** page. The bot prints an invite link at startup:

```
[Bridge] Invite this bot with https://discord.com/api/oauth2/authorize?client_id=...
```

Open that link and pick your server. The permissions it asks for are View Channels, Send Messages, Manage Channels, Manage Messages, Embed Links and Read Message History. Manage Channels is what lets it create and tidy the per-bot channels below. Read Message History looks unnecessary, since the bot never reads conversations, but Discord requires it to pin a message and to check whether anyone has posted in a channel before retiring it.

> **If the Chat Bridge page says permissions are missing**, the bot was invited before it asked for all of them. A Discord bot keeps the permissions it was invited with, so open the invite link again and re-authorise. Discord updates the bot you already have rather than adding a second one. Until then channels still work, but the bot cannot pin a message in them or tidy them up.

### 3. Paste the token

**Chat Bridge** page → **Discord Bot Token** → tick **Accept commands on Discord** → **Save**, then **Stop and Start** the bot. The bridge only attaches when a fresh Steam session comes up.

### 4. Server ID (recommended)

In Discord, turn on **Settings → Advanced → Developer Mode**. Right-click your server name → **Copy Server ID**, and paste it into **Server ID**.

Without this, Discord can take up to an hour to publish your commands the first time. With it, they appear immediately. Worth setting even if you only use it while testing.

---

## Bot channels

Each of your bots gets its own channel, named after it, so traders always know which bot they are talking to. **The channel is the bot.**

```
CARD BOTS
  # low          talks to "Low"
  # high         talks to "High"
  # gem-trader   talks to "Gem Trader"
```

A command typed in `#low` goes to Low and nowhere else. No arguments, nothing to remember.

### Setting it up

1. In Discord, create an empty **category** (right-click in the channel list → Create Category). Call it whatever you like.
2. Right-click the **category heading** → **Copy Category ID**. This is a long number, not the name.
3. Paste it into **Bot Channels Category ID** on the Chat Bridge page and **Save**.
4. Click **Create / update bot channels**.

Every bot you have configured gets a channel, including when you only run one, so the category always reads as a complete list. Each channel gets a pinned line saying which bot it belongs to, and its topic shows live rates and stock.

### It keeps itself in order

| You do this | The bot does this |
|---|---|
| Rename a bot | Renames its channel to match |
| Add a bot | Creates a channel for it |
| Drag a channel out of the category | Moves it back |
| Delete a bot | Removes its now-dead channel |
| Click sync again | Nothing, it never makes duplicates |

### What the bot is allowed to change

Two switches on the Chat Bridge page, both on unless you turn them off.

| Switch | On | Off |
|---|---|---|
| **Remove channels for deleted bots** | A dead room is deleted | It is kept and marked as retired |
| **Rename channels when a bot is renamed** | The channel name follows the bot name | Your own channel names are left alone |

Renaming is the only thing a sync does to a name you may have chosen yourself, which is why it
can be switched off. A channel belongs to its bot by id, not by name, so renaming one by hand
never breaks the link and the bot keeps answering there. After a sync the page says how many
names it left alone, so an idle-looking result is never a silent failure.

**Deleting is careful.** A channel is only ever removed if this bot created it *and* nobody has typed in it. Slash replies are private, so a bot channel normally holds nothing but the pinned line. If a real person has posted there, it is kept and simply marked as retired. A retired channel also stops answering: a command typed in it gets a short note saying the bot that lived there was removed, rather than being quietly answered by whichever other bot happens to be running. You can switch removal off entirely with **Remove channels for deleted bots**.

> Traders can also message the bot directly instead of using a channel. With one bot running that just works. With several, the bot asks which one you meant and lists the channels.

---

## Setting up Telegram

Much shorter, no developer account needed:

1. Open Telegram and message **@BotFather**.
2. Send `/newbot` and follow the two prompts.
3. Copy the token it gives you into **Telegram Bot Token**, tick **Accept commands on Telegram**, **Save**, then Stop and Start the bot.

Traders open your bot in Telegram and type `/` to see every command. The bot's `t.me` link is worked out automatically, you do not need to enter it.

**Running more than one bot?** Discord gives each bot its own channel, which says who you are
talking to. Telegram has no channels, so the trader names the bot on the command itself:

    /stock bot:Low
    /check bot:Low

They do not have to memorise anything. `/botlist` lists every bot with what to type and which
are online, and `/help` repeats it at the bottom whenever more than one bot is running. The name
can go anywhere in the line and is never read as an argument. With a single bot it can be left
off entirely, so a one-bot owner never sees any of this.

A bot whose name contains a space, say "Gem Trader", is reached as `bot:gem-trader`, because the
command line is split on spaces. `/botlist` always shows the form that works.

---

## What changes on Steam

Once a bridge is running, Steam chat stops being a menu and becomes a signpost.

| | Bridge off | Bridge on |
|---|---|---|
| New friend | Full welcome message | Short greeting pointing at Discord or Telegram |
| `!HELP` | The full command list | One line pointing at Discord or Telegram |
| An unknown `!command` | "Unknown command" reply | Silence |
| Someone spamming | Three warnings, then unfriended | Silently timed out, then unfriended |
| Trading commands | All work | Handled on Discord or Telegram instead |

Every message is worded one of **15 different ways**, because sending identical text to everybody is exactly what looks automated. The bot also pauses and shows Steam's typing indicator rather than replying instantly.

**You are exempt.** Admin SteamIDs keep full command access on Steam, so you never lose control of your own bot.

**With no bridge configured, none of this applies.** The bot talks exactly as it always has.

### Telling traders where to go

Two options under **Telling traders where to go**:

- **Point at my profile** (default). The bot says *"the invite is on my Steam profile"* and never types a link. Steam scores accounts that send links, so this is the quieter choice. **Put your invite in your Steam profile summary first**, or traders hit a dead end.
- **Post the actual invite link**. Simpler for traders, at the cost of every message carrying a URL.

Either way, fill in **Server Invite Link** with the `https://discord.gg/...` invite you hand to traders. That field is what arms the whole quiet mode: with nowhere to send people, the bot stays talkative on Steam rather than pointing at nothing.

> The friend-list status line on the **Bot Settings** page now understands `{discord}` and `{telegram}` too, so you can advertise your invite there without the bot sending anything at all.

---

### Offering a Steam group invite

Off by default. Switch on **Offer a Steam group invite** and give it a group ID, and the signpost
gains one closing line:

> Nearly everything runs through Discord now, nicer for everybody trading. The invite is on my
> Steam profile whenever you fancy it.
>
> There is a link on my profile, and I can send you a Steam group invite if you say yes.

**The invite is sent only when that trader replies yes.** Not after a trade, not on a timer, and
never to anybody who has not asked. That last part matters: an invite nobody asked for is what
Steam treats as spam, and it is the bot account that gets reported for it. An earlier version of
this bot invited every trading partner automatically and that is exactly why it was removed.

What counts as yes is deliberately narrow: a short reply such as *yes*, *ok*, *sure*, *invite me*.
A sentence is not a yes, so "yes but only the good ones" gets nothing. A no gets silence rather
than another message. One invite per person, and a yes only counts for 15 minutes after the offer.

The offer line comes in 15 phrasings and the confirmation in another 15, so the pair never repeats.
Leave the switch off and the bot never mentions a group at all.

## How a trader links their Steam account

1. They add your bot on Steam as normal. **The bot only links accounts it is already friends with**, which is what stops it being used to message strangers.
2. They run `/link 7656...` with their SteamID64.
3. Your bot sends them **one** Steam message containing a 6-character code.
4. They reply `/verify ABC123`. That is the only Steam message they will ever get.
5. `/swap` now works, with **every** bot you run, not just the one they used.

### Trade URLs

A trader who also runs `/tradeurl <their Steam trade URL>` can be sent offers by **any** of your bots without adding each one as a friend. Worth suggesting if you run several.

The bot checks the trade URL actually belongs to the account they verified, so nobody can point your offers at somebody else. If they later regenerate their trade URL, the bot notices, forgets the old one, and tells them to run `/tradeurl` again.

---

## Chat Bridge troubleshooting

| What you see | What it means |
|---|---|
| *"That kind of interaction is not handled here"* | **Interactions Endpoint URL is set** in the Discord developer portal. Clear it. |
| *"This command is outdated"* | Discord is still publishing your commands. Set the **Server ID** for instant registration, and press Ctrl+R in Discord. |
| Commands do not appear at all | The bot was invited without the `applications.commands` scope. Re-invite using the link in your Logs. |
| Channels are not created | The bot is missing **Manage Channels** on that category, or the Category ID is a name rather than an id. |
| Duplicate channels | Give the bot **View Channels** on the category. It cannot see what it already made. |

The **Logs** page shows a line the moment any command arrives:

```
discord: interaction received: rates
```

If a trader reports a problem and that line is missing, Discord never reached the bot, so the cause is one of the first three rows above. If it is there, the log will say what happened next.

---

## Chat Monitor

Live feed of Steam chat messages and incoming trade offers, with each trader's Steam ID and the bot's response.

![Chat Monitor](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/ChatMonitor.png)

---

## Logs

Raw bot log output with INFO, WARN, and ERROR entries. One-click clear.

The **🛟 Support Report** button gathers everything support needs — app version, OS, bot state, and the recent log — into one report, copied to your clipboard and saved as a file. Passwords, secrets, and API keys are never included. If something goes wrong, send that one paste instead of screenshots.

![Logs](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/Logs.png)

---

## Getting a License

Visit **[steamtradebots.com](https://www.steamtradebots.com/)** to purchase and activate a license. Paste your key into the License tab and the bot activates instantly — you only do this once, the license is remembered between restarts.

The license is tied to your machine and re-checked automatically while the bot runs. If you are on a time-limited plan you will see a reminder in the app before it expires.

![License](https://www.steamtradebots.com/assets/images/Bots/SteamSwapBot/License.png)

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
