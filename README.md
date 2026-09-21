# google-easter-eggs

## Try these first

These are the most interesting source-backed interactions currently included in the catalog. Search the exact English query on `google.com`; a translated alternative is listed where it is commonly useful.

| Type | Search query | What happens |
| --- | --- | --- |
| Animation | [67](https://www.google.com/search?q=67), [6-7](https://www.google.com/search?q=6-7), [6 7](https://www.google.com/search?q=6+7), or [six seven](https://www.google.com/search?q=six+seven) | The results page briefly wobbles. |
| Animation | [do a barrel roll](https://www.google.com/search?q=do+a+barrel+roll) | The results page rotates 360 degrees. |
| Animation | [askew](https://www.google.com/search?q=askew) | The results page tilts slightly. |
| Animation | [blink html](https://www.google.com/search?q=blink+html) | Matching words in the results blink. |
| Search joke | [recursion](https://www.google.com/search?q=recursion) | Google suggests searching for the same term again. |
| Search joke | [anagram](https://www.google.com/search?q=anagram) | English Search suggests the joke “nag a ram.” |
| Game | [block breaker](https://www.google.com/search?q=block+breaker) | A playable Breakout-style game card appears. |
| Game | [pac-man](https://www.google.com/search?q=pac-man) | A playable Pac-Man card appears. |
| Game | [snake game](https://www.google.com/search?q=snake+game) | A playable Snake card appears. |
| Game | [solitaire](https://www.google.com/search?q=solitaire) | A playable Solitaire card appears. |
| Game | [minesweeper](https://www.google.com/search?q=minesweeper) | A playable Minesweeper card appears. |
| Game | [tic tac toe](https://www.google.com/search?q=tic+tac+toe) | Play against Google or another person on the same device. |
| Game | [memory game](https://www.google.com/search?q=memory+game) | A short sound-and-memory game appears. |
| Interactive toy | [spin a dreidel](https://www.google.com/search?q=spin+a+dreidel) | Spin a virtual dreidel. |
| Interactive toy | [emoji kitchen](https://www.google.com/search?q=emoji+kitchen) | Combine emoji into stickers. |
| Interactive tool | [flip a coin](https://www.google.com/search?q=flip+a+coin) | Flip an animated virtual coin. |
| Interactive tool | [roll a die](https://www.google.com/search?q=roll+a+die) | Roll multiple virtual dice and add modifiers. |
| Interactive tool | [spinner](https://www.google.com/search?q=spinner) | Use a number wheel or fidget-spinner mode. |
| Interactive tool | [animal sounds](https://www.google.com/search?q=animal+sounds) | Play calls from multiple animals. |
| Interactive tool | [metronome](https://www.google.com/search?q=metronome) | Set a BPM and play a metronome. |
| Interactive tool | [color picker](https://www.google.com/search?q=color+picker) | Adjust a color and inspect its values. |

### Editor's pick: Block Breaker

**Block Breaker** is the best starting point. The page-wide animations are clever but over in seconds; this is a complete, replayable game built directly into Search. It is also the strongest proof that this catalog should cover interactive Search experiences, not only one-off visual jokes.

### What do you think?

Do you agree that Block Breaker deserves the top spot? Start a GitHub Discussion to nominate the next featured entry, challenge this pick, or share a reproducible verification for an interaction that is missing from the catalog. Include the search term, country/language, device, date, and a screenshot or recording whenever possible.

Availability can still vary by country, language, device, account, accessibility settings, and Google experiments. Open [`easter-eggs-data.json`](easter-eggs-data.json) for aliases, sources, notes, and verification details.

An interactive and **critically verified** catalog of Easter eggs, games, and visual effects triggered by searches on Google (`google.com/search`).

## Why this repository exists

Searches for “Google Easter eggs” return many nearly identical lists, often generated or rewritten by AI, that mix together:

- effects that still exist today;
- effects that were removed years ago (for example, Zerg Rush and Atari Breakout);
- seasonal effects presented as permanent features;
- third-party sites (especially **elgooG** and **mrdoob.com**) presented as Google features — Google Gravity is the most common example, although it **was never a google.com feature**;
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
  "term": "exact search term",
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

The catalog currently lives in this README. Structured records are kept in [`easter-eggs-data.json`](easter-eggs-data.json).

## Known limitations

- Recent Google Easter eggs are often **promotional knowledge panels** tied to films, series, games, artists, and product launches. They can disappear within weeks, so this catalog prioritizes durable effects, classic games, and Search tools.
- Short CSS/JavaScript animations such as “do a barrel roll” are difficult to capture in a static screenshot because they finish within seconds. The `verification_method` field records that limitation.
- Search results can vary by signed-in account, history, region (`gl`), language (`hl`), device, accessibility settings, and active Google experiments. Relevant differences are recorded in `notes`.

## Contributing

Contributions are welcome, especially:

1. **Retesting `unconfirmed` or `removed` items** with the date, language, region, and device used, plus a screenshot or recording when possible.
2. **Adding new items** using the JSON schema above. Every item must include a verification method; copied lists without an independent test are not accepted.
3. **Updating stale items** when an `active` interaction stops working.

Do not trust any list, including this one, without testing it yourself.

## Disclaimer

This is an independent catalog with no affiliation with Google or Alphabet. “Google” is a trademark of Google LLC. Third-party sites such as elgooG and mrdoob.com are mentioned for identification only and are not endorsed by this project.

