# Measuring Serendipity in Music Recommendation

## Paper

**The Serendiptionnaire: a Questionnaire for Measuring Experienced Serendipity**  
Brett Binst and Annelien Smets  
[arXiv:2610.29487v1](https://arxiv.org/abs/2610.29487) · cs.HC · 21 October 2026

**Paper type:** Questionnaire and measurement-framework research  
**Primary contribution:** A modular instrument for measuring users' *experienced serendipity* when interacting with recommender systems.

## Problem Statement

Serendipity is a desirable outcome in recommender systems, but research has measured it inconsistently. Some studies use novelty as a proxy, some ask whether a recommendation was surprising, and others create their own questionnaire items. These approaches can measure different experiences while all claiming to measure serendipity, making results difficult to compare.

The paper argues that **novelty alone is not serendipity**. An unfamiliar song may be irrelevant, boring, or forgettable. A surprising recommendation may also fail to enrich the listener. Conversely, a familiar song can create a serendipitous experience if it reveals something new or reconnects the listener with an earlier interest.

The authors address this measurement gap by developing the **Serendiptionnaire**, a questionnaire designed to capture the different ways users experience serendipity.

## Central Idea

The authors define experienced serendipity as:

**A fortuitous encounter with content that is both refreshing and enriching.**

The three components are not single yes/no concepts. Each can be fulfilled through several conditions, and different combinations produce different *flavors* of serendipity.

This is the paper's most useful conceptual move: instead of asking whether a recommendation was simply "serendipitous," first specify *what kind* of serendipitous experience the system is supposed to create.

## The Three Components

### 1. Fortuitous — How did the encounter happen?

The paper identifies four possible conditions:

- **Unintentional:** The user encountered something they were not specifically searching for or looking for.
- **Difficult-to-find:** The platform helped surface something the user might otherwise have struggled to discover; this includes the perception of finding a hidden gem.
- **Unexpected:** The content or the fact that it appeared was surprising to the user.
- **Uncovering:** The encounter revealed something from a new perspective. In the updated framework, uncovering also belongs to the refreshing component.

An important revision: **unintentionality is no longer mandatory**. A listener may deliberately open an exploration mode and still experience serendipity when a particular recommendation is unexpected, difficult to find, or revealing in a new way.

### 2. Refreshing — How did the content relate to the user's past listening?

The paper separates three conditions:

- **Novelty:** The item is new to the user. The authors deliberately use concrete ideas such as not having seen or known an item before, rather than relying on the abstract word "novel."
- **Unusualness:** The item differs from the user's normal consumption or typical preferences.
- **Taste-reincarnation:** The item reconnects the user with something they previously liked or evokes nostalgia.

**Novelty and unusualness are different.** A listener may discover a new shoegaze artist who fits their existing taste: novel, but not unusual. They may also hear a familiar artist experimenting with an unfamiliar style: unusual, but not necessarily novel.

Uncovering is cross-cutting: a familiar song can become refreshing when the listener notices a new detail or interprets it differently.

### 3. Enriching — What positive effect did the encounter have?

The seven conditions are:

- **Intrigue:** The content sparks interest or curiosity.
- **Energy:** It recharges, energizes, or motivates the user.
- **Inspiration:** It stimulates creativity, imagination, or new ideas.
- **Impact:** It may have a positive influence on the user's life.
- **Empowering:** It has a positive effect on the user's self-esteem.
- **Usefulness:** It is helpful or may prove useful for a goal.
- **Resonance:** It feels meaningful, moving, or touching.

For music discovery, intrigue and resonance may be especially informative, while energy and inspiration could be useful for particular listening contexts. The instrument is modular, so a study should not automatically include every condition.

## Intended, Afforded, and Experienced Serendipity

The paper distinguishes three connected levels:

- **Intended serendipity:** What the product or research design is trying to achieve.
- **Afforded serendipity:** What the system's design and algorithm make possible.
- **Experienced serendipity:** What the listener actually experiences and evaluates.

This distinction prevents a common recommender-system mistake: assuming that because an algorithm introduces diverse or distant items, users must have experienced meaningful discovery. A system can afford an unusual recommendation without the listener being interested in it.

For my project, this means that a high Explore setting, a low-popularity track, or a large embedding distance is evidence of what the system *served* — not proof of what the listener *experienced*.

## Methodology

The study develops the questionnaire through **27 cognitive interviews**, conducted in three iterative rounds of nine participants each between May 2025 and May 2026.

The researchers purposively sampled for variation in:

- Age
- Education level
- Country of birth
- English proficiency

Participants used familiar recommendation-driven platforms during the study. The sample included Instagram, TikTok, YouTube, Spotify, LinkedIn, RedNote, Zalando, Bol.com, Bilibili, Threads, and Facebook.

The interview procedure had four broad stages:

1. Explain the procedure and obtain informed consent.
2. Assess English proficiency.
3. Observe the participant using a familiar platform in a normal session.
4. Ask the participant to complete the questionnaire while explaining how they interpret and answer each item.

The main techniques were **think-aloud** and **verbal probing**. Participants explained what a question meant to them, what they were considering, and why they selected an answer. Researchers used follow-up probes to clarify ambiguous interpretations, including what terms such as "intriguing" meant to participants.

The interviews were transcribed and coded in MAXQDA. The researchers combined deductive coding using the Question Appraisal System with inductive coding for issues that emerged from participants' interpretations. After each round, they revised the questionnaire and tested the updated version with a new group.

### Why this methodology matters

The authors were not simply checking whether a questionnaire sounded clear to researchers. They were checking whether different people actually understood each item in the intended way. For example, they found that:

- "Hidden gem" needed an explanation for some respondents.
- "Novel" was not understood consistently, so the final questionnaire used more concrete wording.
- "Familiar" and "new" could be confused with unusualness, so novelty and unusualness were separated more carefully.
- "Empowering" was difficult for many participants to understand, so the final scale used self-esteem wording.
- Respondents could confuse the goal of a whole session with the intention behind encountering one specific recommendation.

This is a strong reason to pilot any adapted questionnaire with actual listeners rather than assuming that research terminology is self-explanatory.

## How the Serendiptionnaire Is Scored

This is one of the most important technical details in the paper.

### The questionnaire is modular

Researchers first choose the flavor of serendipity they want to study. They then include only the scales that define that flavor. The authors explicitly state that the full questionnaire is not meant to be administered or scored every time.

### Within a scale: use the maximum item response

Each scale contains several items describing different ways that a condition can be experienced. These items are **not interchangeable reflective indicators** that are expected to correlate. Each item represents a possible expression of the condition.

Consequently:

- Score a condition using the **maximum response across its items**.
- The condition counts as present when at least one item reaches **"somewhat agree"** or higher.
- Weak correlations between items are not treated as a problem.
- Cronbach's alpha and similar internal-consistency measures do not apply to these scales in the way they would for reflective scales.

### Across scales: all defining conditions must be present

The selected conditions of a flavor are combined conjunctively. In other words, each required condition must be met for the flavor to count as present.

The paper's example is **taste-broadening serendipity**:

`Taste-broadening = (at least one fortuitous condition) AND (unusualness) AND (intrigue)`

The final classification for a user and referent is binary: the target flavor was experienced, or it was not.

This is not the same as averaging all questionnaire answers into one general serendipity score. The logic is:

- **OR within a condition:** at least one item expresses that condition.
- **AND across the conditions defining a flavor:** every required condition must be present.

**Implementation caution:** The questionnaire also presents opposite-direction statements for some conditions (for example, the absence of surprise). When implementing the scoring, preserve each item's direction and map it correctly to the condition being tested. Do not treat agreement with an opposite statement as positive evidence for the target condition simply because the raw response is high.

## Choosing the Unit of Evaluation: Track or Listening Session?

The authors stress that the questionnaire must have a clearly defined **referent** — the object the participant is evaluating. All conditions used to classify one experience must refer to the same object.

### Individual recommendation as referent

Evaluate one song at a time. This is useful when the research question is whether a particular recommended track was serendipitous. The same song must satisfy the selected fortuitous, refreshing, and enriching conditions.

The downside is survey burden when evaluating many songs. The authors suggest a flowchart-style process: ask the most discriminative question first and only ask the remaining questions for recommendations that pass that filter.

### Listening session as referent

Evaluate a whole session or sequence of recommendations. This is useful when the system is designed to guide the listener along a discovery journey rather than make one isolated recommendation.

The paper cites a music-recommendation example in which a sequence of songs gradually introduces a listener to a target genre. In that case, the intended taste-broadening experience belongs to the trajectory of the session, not necessarily to every individual song.

However, a session is a more diffuse object to remember and evaluate than a single track. The researchers advise piloting whether participants genuinely interpret the questions at the session level.

**Application to my project:** If the Explore vs. Familiar control changes the mix and trajectory of a batch of recommendations, session-level evaluation is useful. If I want to identify which particular FMA tracks work as discovery candidates, track-level evaluation is more precise. These are different research questions and should not be mixed in one score.

## Strengths

- **Separates novelty from unusualness.** This is essential because a new artist can still fit a listener's existing taste, while familiar music can be encountered in an unusual context.
- **Treats serendipity as multidimensional.** It captures the encounter, the relationship to the listener's past, and the value of the experience.
- **Builds the questionnaire around user interpretation.** Three rounds of cognitive interviews expose ambiguous words and confusing items before the instrument is used more broadly.
- **Provides an explicit scoring procedure.** Researchers are told how to combine responses instead of inventing a generic average.
- **Supports targeted system evaluation.** It can help test whether offline metrics correspond to specific user experiences, rather than treating "serendipity" as one vague construct.
- **Can be adapted to different recommender goals.** A discovery system, a task-oriented recommender, and a taste-deepening experience need not use the same set of scales.

## Weaknesses and Critical Reading

- **Small, purposive interview sample.** Twenty-seven participants across three rounds are suitable for cognitive interviewing and item refinement, but they do not establish how common these experiences are in a wider listener population.
- **The validation evidence is primarily about interpretation.** The paper demonstrates how respondents understand the items through cognitive interviews. It does not report a large-scale psychometric study establishing factor structure, test-retest reliability, or population-level measurement properties. The authors call the instrument validated, but it is important to be precise about the type of validation presented.
- **The questionnaire is not plug-and-play.** The authors explicitly say that items must be adapted to the intended system and research context, then piloted.
- **The framework is not exhaustive.** The authors suggest that conditions such as synchronicity — a meaningful coincidence — could be added in future work.
- **Session-level questions can be harder to answer.** A listener may struggle to summarize an entire listening session, particularly if the session contains many different recommendations.
- **The study is not exclusively about music.** It includes Spotify participants, but the questionnaire was developed across multiple platform contexts. Music-specific wording still needs to be tested with music listeners.
- **Some enriching conditions may be less relevant to a short music recommendation task.** For instance, life impact or usefulness may not be meaningful outcomes for every listening session. Modular selection is therefore important.

## My Takeaways

1. **A recommendation is not successful discovery merely because it is unfamiliar.** The listener should also find it refreshing in relation to their usual consumption and enriching in some meaningful way.
2. **Novelty and taste distance should be measured separately.** A previously unheard track by a familiar artist or within a familiar genre is not the same kind of discovery as a track that challenges the listener's usual preferences.
3. **Serendipity can happen during intentional exploration.** A user can deliberately choose an Explore mode; an individual track can still be unexpected, hard to find, or revealing.
4. **A familiar song can still be serendipitous.** Uncovering can mean noticing something new in a song the listener already knows, rather than discovering a completely new track.
5. **Offline metrics need user validation.** Popularity, novelty, distance from a user profile, and genre deviation are proxies. They need to be tested against what listeners say they experienced.
6. **A single global serendipity score can hide failure modes.** A system might successfully show unusual music but fail to spark interest. The separate conditions reveal that difference.

## Ideas for My Music Recommendation Project

### 1. Define a project-specific flavor: Long-Tail Taste-Broadening Serendipity

A useful research target for an obscure-music discovery system could be:

**Long-tail taste-broadening serendipity = difficult-to-find + unusual + intriguing.**

This is a proposed project-specific flavor, not a named validated scale in the paper. It uses the paper's modular logic:

- **Difficult-to-find:** The listener feels that the platform surfaced a track or artist they would have struggled to discover independently.
- **Unusual:** The recommendation differs from the listener's normal listening patterns or preferences.
- **Intriguing:** The recommendation sparks enough interest to make the listener curious about the track, artist, album, label, scene, or genre.

This definition connects the long-tail objective to an actual user experience. Merely recommending low-popularity tracks would not be sufficient.

### 2. Adapt a small set of questionnaire items for music

The following are **draft adaptations for my study**, not validated Serendiptionnaire items. They should be cognitively piloted with listeners before being used to make research claims.

Use a five-point response scale matching the paper: strongly disagree, somewhat disagree, neither agree nor disagree, somewhat agree, strongly agree.

**Difficult-to-find**

- This session surfaced at least one track or artist I would have found difficult to discover on my own.
- I came across a hidden-gem track or artist that I had not known about or had overlooked.

**Unusualness**

- At least one recommendation differed from the type of music I normally listen to.
- This session moved beyond my typical musical preferences.

**Intrigue**

- At least one track made me curious to explore the artist, album, or scene further.
- At least one recommendation sparked my interest in music I had not previously considered.

**Optional uncovering / taste-deepening**

- I noticed something new in a song or artist I already knew.
- A recommendation changed how I thought about music I previously liked.

For the proposed long-tail taste-broadening flavor, the first three groups are the core. The optional uncovering questions support a separate taste-deepening analysis and should not automatically be folded into the same classification.

### 3. Validate the system's offline metrics against user experience

I could compare the system's computational signals with the listener's responses:

| System-side signal | User-side condition it might predict | Important caveat |
|---|---|---|
| Track or artist popularity / rarity | Difficult-to-find | Low popularity does not prove that a listener sees it as hard to find. |
| Distance from the listener's historical profile | Unusualness | Distance may produce irrelevant recommendations rather than worthwhile exploration. |
| Genre or audio-feature deviation | Unusualness | A feature-space difference is not identical to perceived difference in taste. |
| Unexpectedness or profile-based surprise | Unexpectedness | Surprise alone does not show that the track was enriching. |
| Saves, artist clicks, repeat listens, or follow-up exploration | Possible behavioral evidence related to intrigue | These are useful behavioral signals, but they are not direct measurements of experienced serendipity. |

The evaluation question becomes: **Which computational signals actually predict the specific experiences we want to create?**

### 4. Compare Familiar and Explore recommendations

This could provide a concrete evaluation for the Explore vs. Familiar control:

1. Ask listeners to complete comparable sessions under a Familiar-oriented setting and an Explore-oriented setting.
2. Keep the referent consistent: either evaluate every sampled track separately or evaluate each complete session.
3. Collect the adapted questionnaire responses immediately after listening, while the session is still fresh.
4. Apply the paper's scoring logic rather than averaging every item into one undifferentiated score.
5. Compare the proportion of sessions (or tracks) that satisfy the defined long-tail taste-broadening flavor.
6. Report recommendation quality alongside the serendipity outcome; exploration should not be treated as successful when it only increases irrelevance.

Useful complementary measures for my recommender include Precision@K or NDCG@K where relevance labels are available, catalogue coverage, long-tail exposure, artist diversity, novelty, and listening follow-through. These complement rather than replace the user-reported measure.

### 5. Use it to make the research claim more defensible

Instead of claiming:

> The system improves serendipity because it recommends obscure or dissimilar tracks.

A stronger, testable claim would be:

> The system is designed to increase long-tail taste-broadening opportunities. We evaluate whether its recommendations are perceived as difficult to find, unusual relative to listeners' preferences, and sufficiently intriguing to encourage further musical exploration.

That distinction separates the algorithm's objective from the listener's actual experience.

## Further Research Connections

The paper itself points to two closely related works:

- Binst, B., Michiels, L., and Smets, A. (2025). [What is Serendipity? An Interview Study to Conceptualize Experienced Serendipity in Recommender Systems](https://doi.org/10.1145/3699682.3728325). This is the conceptual work behind the three-component framework.
- Binst, B., Maes, U., Willemsen, M. C., and Smets, A. (2026). [Let Me Introduce You: Stimulating Taste-Broadening Serendipity Through Song Introductions](https://arxiv.org/abs/2604.08385). This is a particularly relevant music-discovery direction cited by the paper.

## Final Research Note

The Serendiptionnaire changes how I should think about evaluating my recommender. The objective is not simply to increase novelty, distance from a user's profile, or the percentage of obscure tracks. Those signals describe what the algorithm delivers. The more interesting question is whether a listener experiences the recommendation as an unexpected or hard-to-find encounter, finds it different from their normal taste, and becomes genuinely curious about exploring further.

For my project, the most actionable contribution is a user-centred evaluation layer for long-tail discovery. It could help determine whether the Explore setting creates meaningful taste-broadening experiences or merely pushes users toward unfamiliar music they do not want to hear.
