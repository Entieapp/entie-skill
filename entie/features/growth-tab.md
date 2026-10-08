# Growth Tab

## What it is

The **Growth Tab** is a curated library of educational articles designed to help each partner deepen their understanding of relationships, intimacy, and themselves. Articles are personalized by gender — men and women each see a different set of content tailored to their perspective and needs.

Articles are organized into four categories, each addressing a different dimension of relationship growth. The tab appears in the main bottom navigation and refreshes automatically when the user's gender changes.

---

## How it works

### Content delivery
- Articles are bundled in the app (no network call required to list them)
- Content loads from `Articles/manifest.json` which defines categories, articles, audiences, and available languages
- The app resolves the user's preferred language (`en` / `ru`) against the manifest and falls back to the default language
- Article bodies are Markdown files stored under `Articles/<article-id>/<language>.md`

### Audience filtering
- **Men** see articles where `audience: "male"`
- **Women** see articles where `audience: "female"`
- The filter is reactive: if the user updates their gender in settings, the Growth Tab reloads with the new audience's content

### Categories (same for both audiences)
| Category ID | English Title | Russian Title | Focus |
|-------------|---------------|---------------|-------|
| `intimacy` | Intimacy | Секс и близость | Sexual connection, desire, arousal, communication in bed |
| `long-run` | Long Run | Крепкие отношения | Long-term relationship skills, conflict, values, dating your partner |
| `show-up` | Show Up | Я в отношениях | Personal responsibility, boundaries, self-awareness, communication |
| `in-sync` | In Sync | Цикл и этапы жизни | Cycle awareness, life-stage transitions (pregnancy, menopause) |

### Article structure
Each article has:
- **id** — unique identifier (used for analytics and deep links)
- **title** — full title shown on the detail screen
- **shortTitle** — compact title shown on the Growth card carousel
- **imageName** — asset name in `ArticleImages.xcassets` for the cover image
- **language** — resolved language code (`en` or `ru`)
- **audience** — `male` or `female`
- **category** — one of the four category IDs above

---

## Who uses it

- **Both partners** — each sees their own gender-specific library
- **Primary use case:** Self-directed learning during quiet moments; reference during conversations
- **Secondary use case:** Partner shares a specific article via deep link or conversation starter

---

## Why it matters

| Pain point | How Growth Tab addresses it |
|------------|------------------------------|
| "I don't understand why my partner reacts this way" | Articles explain the *other* gender's experience (e.g., men learn how women's arousal works; women learn why men need respect) |
| "We keep having the same fight" | `long-run` and `show-up` categories teach conflict patterns, memory differences, and communication tools |
| "Sex has become routine / stressful" | `intimacy` category covers desire mismatch, performance anxiety, foreplay, shame, and novelty |
| "I feel like I'm doing all the work" | `show-up` category addresses people-pleasing, boundaries, and reciprocal effort |
| "I don't know what I need or how to ask" | Both audiences get articles on identifying and expressing desires directly |

---

## How to talk about it

### Do
- Frame it as **a personal library**, not homework: *"Your Growth tab has articles picked for you"*
- Emphasize **privacy**: *"Only you see your articles — your partner has their own set"*
- Use **approachable, non-clinical language**: *"Understanding her desire"*, *"Why he pulls away"*
- Highlight **actionability**: *"One small thing to try tonight"*, *"A conversation starter for Sunday morning"*
- Mention **bilingual support** (EN/RU) when relevant

### Don't
- ❌ Call it "education," "courses," "lessons," or "therapy"
- ❌ Imply one gender's content is "better" or "more advanced"
- ❌ Use medical/clinical terms (dysfunction, disorder, treatment)
- ❌ Suggest articles replace professional help for serious issues
- ❌ Gender-stereotype beyond what the content actually covers (the articles themselves are nuanced)

### Example copy

**App Store / marketing:**
> *Growth — your private library of straight-talk articles on intimacy, communication, and showing up for each other. Different for him, different for her. Always there when you need it.*

**In-app empty state (if no articles for some reason):**
> *Your Growth library is loading…*

**Push notification (when new articles are added):**
> *New in Growth: "Why She Stays Silent in Bed" — understand what she's not saying and how to make it safe to share.*

---

## Article inventory (as of manifest v1, exported 2026-10-01)

### For Men (audience: male) — 23 articles

**Intimacy (13)**
- Why She's "Not in the Mood": What Really Shuts Down Her Desire and How to Help Her Relax
- Sex on Autopilot: How to Bring Presence Back to Intimacy
- Why She Doesn't Tell You What She Wants in Bed, and How to Create a Safe Conversation
- Desire Grows Out of Safety: Why She Opens Up Only With Someone Who Won't Judge Her
- Why She Stops Feeling Desire: Respect, Trust, and the Sense of Being Wanted
- Foreplay Starts in the Morning: How to Stay More Than Roommates and Look Forward to Each Other Again
- Flirting With Your Own Wife: How to Show Her You Want Her Again
- Finishing Fast Isn't a Life Sentence: How to Take Back Control and Let Go of the Anxiety
- When Your Erection Lets You Down: How to Get Through It Together
- Porn, Comparisons, and Borrowed Scripts: Getting Your Taste for Real Intimacy Back
- What's the Rush? Why a Woman's Body Needs More Time
- The First Ten Minutes After Being Intimate: Why They Matter More Than the Sex Itself
- She Needs Connection: Why the Man Who Invests in It Comes Out Ahead

**Long Run (4)**
- Why She Remembers That Fight and You Don't: How Memory for Conflict Works
- A Date With Your Wife: Getting Back That "Us Against the World" Feeling
- How to Talk With Her About What's Real Instead of How the Day Went
- Your Values Are Where Your Time Goes

**Show Up (5)**
- Where We're Headed: Why a Man's Goals Spark Desire and Shape a Couple's Future
- How to Say "No" to the Woman You Love and Stay a Partner She Can Rely On
- Why People-Pleasing Kills Attraction: The Cost of Constant Concessions
- When It's Hard to Breathe Around Your Partner: Belittling, Guilt, and Control
- Jealousy or Care: When Control Hides Behind Love

**In Sync (1)**
- What a Man Gains from Knowing His Partner's Cycle: A Safer Relationship and Care That Fits

---

### For Women (audience: female) — 18 articles

**Intimacy (8)**
- Why Care Doesn't Stop Things Cooling Off: What Really Keeps Passion Alive
- Foreplay That Lasts All Day: How to Keep Sensual Anticipation Alive
- Why You Need More Time, and How to Get It
- Voice, Sounds, and Compliments: How to Sound Natural and Sexy in Bed
- An Intimate Evening: Low Light, a Sensual Kiss, and Trying Something New Safely
- Your Pleasure Isn't a Test: How to Let Go of Control and Stop Faking It
- Where Shame About Your Desire Comes From, and How to Rethink It
- Sexual Magnetism: How to Radiate Sensuality Every Day and Spark Passion

**Long Run (6)**
- He Loves You, but You Don't Feel It: Understanding His Language of Care
- He's Not a Mind Reader: How to Say What You Want Directly
- He Forgot. That Doesn't Mean He Doesn't Care
- The Respect He Feels
- Gaslighting and Belittling: How to Spot Manipulation and Trust Yourself Again
- When the Storm Dies Down: Why the End of the Honeymoon Phase Is Only the Beginning

**Show Up (4)**
- When the Past Overshadows the Present: How to Stop Projecting Old Hurts
- Jealousy or Control? Where Care Ends and Domination Begins
- If You're Afraid of Him
- Chronic Complaints and Black-and-White Thinking: How a Scarcity Mindset Destroys Closeness

**In Sync (0)**
- *(No articles currently — this category is primarily relevant for men learning about their partner's cycle)*

---

## Technical notes for writers

- **Deep links** use the article `id` — format: `entie://growth/<article-id>`
- **Analytics events:** `growth_article_opened` (params: `article_id`, `category`, `audience`), `growth_category_viewed`
- **Localization:** All titles and short titles exist in both `en` and `ru` in the manifest; article bodies are separate `.md` files per language
- **Adding content:** Edit `Articles/manifest.json` and add corresponding `.md` files — no code changes needed
- **Preview in Xcode:** `GrowthView_Previews` registers a mock `ArticlesUseCase` with the real repository pointing to the bundled manifest