# game-title-memorability-score

Scores how memorable a single video game title is. A great title sticks in the mind — it is easy to remember, easy to share in conversation, and easy to search for. This function evaluates whether a title can survive in the wild: standing out on a crowded storefront page and being findable by someone who heard it mentioned once in passing.

## Input

The function accepts a single required field:

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `title` | string | Yes | The video game title to score, as it would appear on a storefront page, in conversation, or in a search bar. |

**Example inputs:**
- `{ "title": "Hollow Knight" }`
- `{ "title": "Celeste" }`
- `{ "title": "Slay the Spire" }`
- `{ "title": "Tom Clancy's Ghost Recon Advanced Warfighter" }`

## Output

A scalar score between **0** and **1**, where:
- **Scores near 1.0** indicate a highly memorable title — distinctive, compact, and sonically satisfying.
- **Scores near 0.5** indicate a moderately memorable title with strengths in some areas but weaknesses in others.
- **Scores near 0.0** indicate a title that is generic, unwieldy, or flat-sounding — unlikely to be remembered or shared.

The final score is the average of three sub-scores, one for each evaluated quality.

## What It Evaluates

The function evaluates memorability across three core qualities:

### 1. Distinctiveness

Does the title stand apart from the crowd? A distinctive title feels like it belongs to one thing and one thing only — it resists confusion with other games. Titles built from overused words and familiar constructions (e.g., "Dark Quest," "Battle Zone") score lower because they are interchangeable with countless others. Titles that feel specific and singular (e.g., "Hollow Knight," "Hades," "Outer Wilds") score higher. However, a title that is so strange it becomes alienating or unpronounceable has overshot the mark — the goal is to be singular, not bizarre.

### 2. Compactness

Does the title express its identity efficiently? Every additional word and syllable works against recall — longer titles are harder to remember, harder to speak aloud, and harder to type into a search bar. Tight titles of one to three words that land with clarity score well, while sprawling titles with many words or cumbersome phrasing score lower. However, compactness is not mere brevity: a title so vague it could refer to anything (e.g., "Game," "Run," "World") has achieved brevity at the cost of meaning. True compactness is compression without loss — short, but still evocative of something specific.

### 3. Sonic Resonance

Does the title sound right when spoken aloud? Some titles have a rhythm, musicality, or phonetic weight that makes them satisfying to say and natural to recall. Human memory is deeply tied to sound — we remember phrases that have cadence and words that feel good in the mouth. "Slay the Spire" sticks through percussive alliteration. "Dead Cells" snaps with two hard syllables. "Stardew Valley" rolls with gentle softness. Titles with strong sonic resonance lodge in the ear after a single hearing; titles that sound flat or clunky get no such advantage.

## Use Cases

- **Indie developers** choosing between candidate names for a new project can pressure-test each option and compare scores.
- **Publishers** evaluating a portfolio of upcoming releases can flag titles that risk being lost in marketplace noise.
- **Game jam teams** brainstorming names can get a quick signal about which ideas have real staying power.
- **Marketing teams** can use the score to assess whether a title will travel well through word of mouth, social media, and search.
- **Comparative analysis**: score multiple title candidates side by side to identify which is most likely to be remembered, shared, and searched for.

## Philosophy

Memorability lives at the intersection of all three qualities. A title that is distinctive but sprawling will be recognized but not recalled. A title that is compact but generic will be easy to say but impossible to find. A title that sounds beautiful but blends into a crowd will please the ear and then be forgotten. The most memorable titles are uniquely their own, efficient in expression, and satisfying in sound — and that is what this function measures.