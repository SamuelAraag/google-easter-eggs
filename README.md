# google-easter-eggs

An independent, source-backed catalog of Google Search Easter eggs, games, and visual interactions, with direct links and reproducible verification.

## Contributing via Discussions

All contributions and catalog updates are centralized exclusively in [GitHub Discussions](https://github.com/SamuelAraag/google-easter-eggs/discussions).

If you discover a new interaction, notice that an active one changed or stopped working, or wish to suggest improvements, open a discussion thread.

### Verification requirements

To allow reproducible verification, include the following details in your post:

- **Query:** exact search term
- **Observed effect:** description of what appears or animates
- **Environment:** browser, operating system, interface language (`hl`), and region (`gl`)
- **Test date:** YYYY-MM-DD
- **Visual proof:** clean screenshot or clip (cropped to the search card, with no personal data or email visible)
- **Source:** URL of an independent report, article, or forum thread

Once verified and discussed, approved items are curated and added directly to [`easter-eggs-data.json`](easter-eggs-data.json).

## Quick start

Five representative interactions to test right away. Search the query on `google.com` (English interface recommended for the most consistent results):

| Type | Search query | Expected effect |
| --- | --- | --- |
| Animation | [67](https://www.google.com/search?q=67) | The results page briefly wobbles. |
| Animation | [do a barrel roll](https://www.google.com/search?q=do+a+barrel+roll) | The results page rotates 360 degrees. |
| Animation | [askew](https://www.google.com/search?q=askew) | The results page tilts slightly. |
| Game | [block breaker](https://www.google.com/search?q=block+breaker) | Playable Breakout-style game directly in Search. |
| Search joke | [recursion](https://www.google.com/search?q=recursion) | Google asks "Did you mean: recursion", linking back to the same search. |

The full catalog of documented games, animations, and search tools is maintained in [`easter-eggs-data.json`](easter-eggs-data.json).

### Featured interaction: Block Breaker

**Block Breaker** is an arcade game rendered inside a Search card. While many visual Easter eggs run for only a few seconds, this entry is a playable mini-game embedded directly in Search results.

To nominate the next featured entry, challenge this pick, or discuss new interactions, join the conversation in [GitHub Discussions](https://github.com/SamuelAraag/google-easter-eggs/discussions).

## Why this repository exists

Searches for "Google Easter eggs" return many nearly identical lists, often generated or rewritten by AI, that mix together:

- effects that still exist today;
- effects that were removed years ago (for example, Zerg Rush and Atari Breakout);
- seasonal effects presented as permanent features;
- third-party sites (especially **elgooG** and **mrdoob.com**) presented as Google features: Google Gravity is the most common example, although it **was never a google.com feature**;
- items that no longer work in any real Search result, despite being described as active.

This project separates those categories by recording the search term, observed behavior, date, and verification method instead of copying existing lists.

## How each item is verified

Each entry in [`easter-eggs-data.json`](easter-eggs-data.json) is tested manually (or by an agent controlling a real browser) on `www.google.com/search`, without a relevant signed-in search history. When possible, the term is tested across more than one language or region.

### Status definitions

| Status | Meaning |
|---|---|
| `active` | Confirmed working on the verification date and tested directly. |
| `seasonal` | Only works during a specific date, event, holiday, anniversary, or launch. |
| `removed` | Previously documented, but not reproduced on the verification date despite trying term variations. |
| `unconfirmed` | Appears in popular lists or AI answers, but could not be reproduced reliably. It may be discontinued, region/account restricted, or inaccurate. |
| `not-google` | The effect is real, but runs on a third-party site that imitates Google (for example, elgooG or mrdoob.com). Searching on `google.com/search` does not produce it. |

An `unconfirmed` item is **not necessarily false**. It means only that reproduction was not reliable on the recorded date. Sources making the contrary claim are listed in the item's `source` field.

## Item schema

```json
{
  "id": "short-identifier",
  "term": ["exact query", "alias or translated variant"],
  "category": "game, calculator, tool, animation, myth...",
  "effect": "what should happen",
  "how_to_test": "step-by-step reproduction instructions",
  "status": "active | seasonal | removed | unconfirmed | not-google",
  "verified_date": "YYYY-MM-DD",
  "verification_method": "where and how it was tested",
  "source": ["consulted sources"],
  "notes": "language, device, region, and other caveats"
}
```

## Catalog format

The structured catalog in [`easter-eggs-data.json`](easter-eggs-data.json) is the single source of truth for this project. It tracks verification dates, sources, aliases, and known caveats for every item.

## Variations and limitations

Google Search interactions vary depending on several factors:

- **Region and language:** Some terms require English (`hl=en`) or specific regional endpoints (`gl`) to trigger.
- **Account personalization and experiments:** Signed-in accounts may receive experimental interfaces or A/B tests where specific cards do not appear.
- **Accessibility settings:** Reduced-motion preferences in your browser or operating system disable or soften animations such as `67` and `do a barrel roll`.
- **Promotional lifespan:** Promotional Easter eggs tied to films, games, or events frequently disappear within weeks. This catalog prioritizes durable features and permanent tools.

## Privacy

Clicking search links sends query parameters directly to Google Search (`google.com/search`). This repository does not host analytics, collect queries, set cookies, or track user interaction.

## Disclaimer

This is an independent catalog with no affiliation with Google or Alphabet. "Google" is a trademark of Google LLC. Third-party sites such as elgooG and mrdoob.com are mentioned for identification only and are not endorsed by this project.
