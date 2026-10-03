# Feature: Relationship Health Score

> Also referred to internally as **Couple Health Score**. The canonical name is **Relationship Health Score**.

## What it is

A single number from **0 to 100** that reflects the current state of the couple's relationship. It is calculated inside the app and is **never shown to users as a number**. Instead, it drives the illustration on the Dashboard and gives the AI service context about the relationship.

## How it works

### Inputs

1. **Three check-in questions answered by the woman** (the partner whose state is tracked):
   - *How secure do you feel in this relationship?*
   - *How desired do you feel in this relationship?*
   - *How open do you feel with your partner?*
2. **Internal app signals.** The app also factors in data from other features in its own calculations, for example [Daily Logging](daily-logging.md) and [Cycle Tracking](cycle-tracking.md).

These inputs produce one score, 0–100.

### Measurement cadence and daily decay

- **Every 30 days** the woman answers the three questions again. Each round is a fresh **snapshot** of the relationship and resets the score to a newly calculated value.
- **The score is not static between snapshots.** Starting the day after a measurement, it **decreases by 0.2 points every day** on its own, until the next measurement brings new data. Over a full 30-day cycle that adds up to about **6 points**.
- The idea: without new input, Entie assumes the relationship slowly drifts if nobody invests in it, so the number gently goes down rather than freezing.
- The score never goes below 0.
- Because of the decay the score can be fractional (e.g. 67.4). It falls into the range that contains its whole-number part (67.4 → 60–69).

### Where the score is used

- **Dashboard illustration.** The scene of the couple on the Dashboard changes with the score: they might walk hand in hand, side by side, or on separate paths. The exact mapping is handled in the app and is not documented here.
- **AI service (via MCP).** When the AI service (the backend behind every AI feature: [Daily AI Tip](daily-ai-tip.md), [AI Chat](ai-chat.md), etc.) requests the Relationship Health Score, the MCP server returns **the description text for the range the score falls into** (see below), not just the number.

## Score ranges

The descriptions below are exactly the text the MCP server returns to the AI service for each range. Ranges are inclusive.

### 0–9

Total disconnection. The relationship has effectively collapsed: partners live like strangers or open adversaries, with no warmth, trust or goodwill left, and communication is either hostile or has stopped altogether. There is no sex and almost no physical touch. It is very likely that one or both partners are already seeking closeness outside the relationship, emotionally or physically, and separation is either underway or imminent.

### 10–19

Critical disconnection, close to breaking up. Resentment and emotional distance dominate; conflict is constant or replaced by cold silence, and partners no longer feel like a team. There has been no sex for months, or it is extremely rare and joyless. There is a high risk that one partner is seeking intimacy outside the relationship, and if the couple has not split yet, a breakup is likely soon.

### 20–29

Severe crisis. The couple stays together mainly for external reasons such as a shared mortgage, children, finances, habit or fear of being alone, not because they are happy together. Arguments are frequent and there is little joy or appreciation. Sex happens once every few months or even once a year; when it does, it is routine and narrow, and oral sex and other non-routine intimacy are absent or refused.

### 30–39

Strained relationship. Tension is in the air most of the time and partners argue often or avoid each other; there is little happiness, and staying together feels more like a habit or obligation than a choice. Sex happens roughly once a month, feels routine and lacks desire; oral sex is usually refused, often explained as 'I just don't like it', which typically reflects low desire and low emotional safety rather than pure preference.

### 40–49

Below average. The relationship works on the surface but feels flat and a bit worse than most couples: life is dominated by routine, chores, kids and money, with little flirting, excitement or curiosity about each other. There are no constant fights, but nobody is actively leading the relationship forward; no one plans dates, confidently initiates intimacy or brings new energy, so things drift. Sex happens one to three times a month, is predictable, and one partner (often the woman) has noticeably lower desire.

### 50–59

Stable but cooling. The couple generally gets along, with basic respect, care and occasional good moments, and conflicts usually get resolved, but the spark is fading and partners have started taking each other for granted. Desire is lower than it used to be; sex happens roughly two to four times a month and sticks to the familiar. Without conscious effort this couple tends to slide into routine, but with a bit of attention and novelty it can easily move up.

### 60–69

Average, settled routine. A typical long-term relationship: partners are a functional team sharing a home, plans and often a mortgage and kids, and they live together without major conflict. There is no deep unhappiness, but not much happiness or passion either; the passion has largely faded. Sex happens roughly once a week or a bit less, often more as an obligation or 'marital duty' than mutual desire, with limited pleasure and variety.

### 70–79

Good connection. Partners like each other, feel attracted, enjoy time together and are generally happy. Sex is regular, about once or twice a week, and still brings real pleasure to both, with some variety and openness, including oral sex. This level usually holds for one of two reasons: either the relationship is still fairly new and the honeymoon hormones keep the passion alive, or at least one partner (often the man) actively invests, leads and keeps attraction alive.

### 80–89

Strong, happy relationship. There is a lot of affection, trust, laughter and a clear feeling of being on the same team, and the woman (or the partner whose state is tracked) feels happy and desired. Sex is frequent, several times a week, enjoyable and varied, and oral sex is a regular part of intimacy. Either the couple is in a passionate early phase, or, in a long-term relationship, at least one partner (often the man) knows what he is doing and skillfully keeps passion and novelty alive.

### 90–100

Exceptional, thriving relationship with a deep emotional bond. Partners feel truly happy, safe and deeply desired; the woman is clearly fulfilled and happy in the relationship. Sex is very frequent, passionate, generous and mutually satisfying, with lots of variety and frequent oral sex. This is either the peak of a fresh, hormone-fuelled romance or a rare long-term couple where at least one partner (often the man) is excellent at leading the relationship and keeping passion alive year after year.

## Who uses it

- **The woman** answers the three questions.
- **Both partners** see its effect indirectly through the Dashboard illustration and the AI-generated content.
- **The AI service** reads the range description as context.

## Why it matters

It gives the AI an honest, compact picture of where the relationship really is, so tips and conversations match the couple's actual situation instead of sounding generic. On the Dashboard it turns an abstract state into a simple, gentle visual.

## How to talk about it

### Important: internal text only

The range descriptions are **internal context for the AI**. They are intentionally blunt, include explicit statements about sex, and contain gendered generalizations. They **must never be shown, quoted or paraphrased to users** and must not appear in marketing, App Store copy, support replies or notifications. Any user-facing content shaped by the score still follows [`../brand/guardrails.md`](../brand/guardrails.md) and [`../brand/voice-and-tone.md`](../brand/voice-and-tone.md).

### Lead with (user-facing)

- A gentle reflection of how the two of you are doing
- Something you notice through the Dashboard scene, not a grade

### Avoid

- Showing or mentioning the number, or calling it a "score", "rating" or "grade" in user-facing copy
- Framing the relationship as failing, or one partner as the problem
- Any wording from the range descriptions

## Edge cases worth knowing

- With few check-ins or sparse data, the score is less reliable; AI content should lean on other context.
- A low score is a reason for the AI to be warmer and more careful, never alarming. If content hints at crisis or abuse, the mental health guardrails apply.
