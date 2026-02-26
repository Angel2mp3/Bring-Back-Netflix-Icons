# Bring Back Netflix Icons

> A powerful userscript that brings back **985 retired Netflix profile icons** across 103 shows and categories — set server-side, so they appear on every device you own.

**Author:** [Angel](https://github.com/Angel2mp3) ❤️ &nbsp;|&nbsp; **Version:** 1.0.0 &nbsp;|&nbsp; **License:** MIT

---

## How It Works

Netflix retires profile icons from its selection UI but usually keeps them fully functional on their server. When you apply a retired icon via Netflix's own GraphQL API (`updateProfileInfo`), it:

- Gets saved to your account, **not your browser**
- Shows up on **every device** — TV, phone, tablet, web
- Looks and behaves exactly like any current Netflix icon

This script surfaces a browseable gallery of those retired icons and applies them using Netflix's own API.

<img width="1138" height="857" alt="image" src="https://github.com/user-attachments/assets/fe55d724-1c61-4dc3-95ab-8988679a7e1e" />

---

## Features

- **985 retired icons** across **103 shows and categories**
- Browse gallery organized by show with icon images and character names
- **Search** by icon name or show
- **Filter** by show/category dropdown
- **Manual Key Entry** tab — paste any avatar key directly
- **Profile selector** built into the toolbar — switch profiles without leaving the modal
- Only activates on Netflix settings pages (`/settings/...`) — zero impact on browsing
- Clean dark UI styled to match Netflix

### Shows & Categories Included

A Series of Unfortunate Events, Arcane: League of Legends, Asterix & Obelix, Avatar: The Last Airbender, B: The Beginning, Beauty in Black, Big Mouth, BoJack Horseman, Bridgerton, Bright, Bubble, Captain Underpants, Christmas Chronicles 2, Cobra Kai, Cowboy Bebop, Dark, Elite, Emily in Paris, Fuller House, Gabby's Dollhouse, Heartstopper, Heartbreak High, Jurassic World: Chaos Theory, KPop Demon Hunters, Leo, Lost in Space, Lupin, Maya and the Three, Money Heist (La Casa de Papel), My Little Pony, Netflix Classic Icons, On My Block, One Piece, Orange Is the New Black, Outer Banks, Over The Moon, Pokémon Concierge, Project Mc2, Queer Eye, Santa Clarita Diet, Sesame Street, Sex Education, Shadow and Bone, Shaun the Sheep, She-Ra, Sonic Prime, Spirit Riding Free, Spy Kids: Armageddon, Squid Game, Stranger Things, Super Monsters, The Believers, The Crown, The Dark Crystal, The Dragon Prince, The Sandman, The Sea Beast, The Umbrella Academy, The Witcher, Transformers: War for Cybertron, True and the Rainbow Kingdom, Vivo, Voltron, Wednesday, and more.

---

## Installation

### 1 — Install a Userscript Manager

| Recommended Extension's |
|---|
| [Violentmonkey (Open Source)](https://violentmonkey.github.io/)
| [Tampermonkey (Closed Source)](https://www.tampermonkey.net/) |

### 2 — Install the Script

[![Install Script](https://img.shields.io/badge/Install-Bring%20Back%20Netflix%20Icons-E50914?style=for-the-badge&logo=tampermonkey&logoColor=white)](https://raw.githubusercontent.com/Angel2mp3/Bring-Back-Netflix-Icons/main/Bring-Back-Netflix-Icons.user.js)

Click the button above — your userscript manager will automatically detect the script and prompt you to install.

---

## Usage

1. Log in to [netflix.com](https://www.netflix.com)
2. Go to edit your profile
3. A **red floating button** will appear in the bottom-right corner
4. Click it to open the icon gallery
5. Use the **Profile** dropdown in the toolbar to pick which profile to update
6. Browse or search for an icon → click it to select → click **Apply Selected Icon**
7. Reload the page — your new icon is live on all your devices!

### Manual Key Entry

Have an avatar key from an external source?

1. Open the modal → click **Manual Key Entry**
2. Paste the key in the format: `AVATAR|UUID|locale|country|showId`
3. Click **Apply Icon**

---

## The Avatar Key Format

```
AVATAR|<uuid>|<locale>|<country>|<showId>

Example: AVATAR|1d1a12d0-3cb9-11ec-b5ae-0e5d81c04d65|en|US|81435227
```

| Part | Description |
|---|---|
| `uuid` | Unique ID for the specific icon |
| `locale` | Language code (`en`, `de`, `fr`, etc.) |
| `country` | Country code (`US`, `GB`, `NZ`, etc.) |
| `showId` | Netflix's internal show/content ID |

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Floating button doesn't appear | Make sure you're on a change avatar/edit profile page |
| "Authentication failed" | Confirm you're logged in to Netflix |
| "No profile selected" | Use the Profile dropdown in the toolbar or navigate to a profile edit page |
| Icon applied but didn't change visually | Hard-refresh the page (`Ctrl+Shift+R` / `Cmd+Shift+R`) |
| Icon applies but resets later | This is rare — try re-applying; some older keys may be fully retired server-side |
| Script not running | Check that your userscript manager is enabled and the script is active |

---

## How the API Works

Netflix exposes a GraphQL endpoint at:
```
https://web.prod.cloud.netflix.com/graphql
```

The script calls the `updateProfileInfo` mutation with a persisted query hash and passes the avatar key as the `userAvatarName` field. Because this is Netflix's own API with your own session cookie, the icon is saved to your account with no external data leaving your browser.

---

## Credits

- Built and maintained by [Angel](https://github.com/Angel2mp3)
- The Biggest possible thanks to Rchuncleskeleton, Tarowo, and everyone else who chipped in on their and other similar projects, this script wouldnt have been possible without all of you!
- Avatar keys sourced from the [Netflix Profile Icons Compilation Project](https://www.reddit.com/r/netflix/comments/13h9uhr/netflix_profile_icons_compilation_project/) and community research on the Netflix and related subreddit's
- More Avatar keys and icon images from [Rchuncleskeleton](https://docs.google.com/spreadsheets/u/0/d/1T5q4qNTFOiU-45iTDUDDkxsj_Hb9S9mZpg4GyLNYarw/htmlview) 
- API method inspired by [tarowo's Netflix Avatar UUID Changer](https://github.com/ilovecats2342/NetflixAvatarUUIDChanger)
- Some inspiration from this extension though a reason for making this project was because this extension is ONLY available on chrome and is closed source to knoweldge, my project is neither [Restore Retired Netflix Profile Icons](https://chromewebstore.google.com/detail/restore-retired-netflix-p/alpmhadlelgmdgahangpkfnnpbeeagep)

---

## Disclaimer

This project is not affiliated with, endorsed by, or sponsored by Netflix. All Netflix profile icons and show imagery are property of Netflix, Inc. and their respective rights holders. Use at your own discretion.
