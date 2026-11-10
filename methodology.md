# Fragrance ranking methodology

## Purpose and reference creators

Build a readable guide that helps compare mainstream designer, niche and affordable alternatives using attributable evidence. Scores describe a declared model and research population. They are not a measured probability that a stranger will find the wearer attractive.

The visual reference is *The Modern Man's Fragrance Guide*, sold by Theophilus Aladejebi, known as Tai / @definitelytai. Its public listing emphasizes practical selection and budget guidance. The screenshot and the user's comments suggest an interest in clear presentation, concrete comparisons and alternatives that earn their place on merit. This is an interpretation of the user's preferences; the paid guide has not been purchased or read.

Prince Tafah / @warrentafah is another user-selected reference, especially for comparisons involving alternatives. Admiration determines which original material to inspect first. It does not grant a numerical credibility bonus to every recommendation.

## Candidate selection

Fragrantica is the primary discovery source. The user's current acquisition rule is the first 500 entries of one combined male + unisex search sorted Most popular, followed by selective research on worthwhile alternatives. Do not split 500 into category quotas, collect 500 per category, sort by raw rating instead, or equate a masculine impression with the source's marketing label. This deliberately bounds the research population; it does not establish the world's best 500 fragrances.

The API.SH combined snapshot originally collected 1,000 cached records before the scope narrowed. Only positions 1-500 are the active base. Cached later records may supply paired metadata for an alternative, but cannot expand the base. The older handpicked 54-candidate pilot and rotating discovery queue are separate historical work.

Keep immutable IDs, concentration, brand, release year when verified, regional naming and source IDs. A newer flanker is a separate entry. A production-batch or formula change needs dated evidence; do not assume that every review describes the current formula.

Page links are discovery leads. Only a clearly labeled similarity result supports a similarity relationship. Similarity does not establish legal copying, identical performance or equal appeal. Alternatives may outrank an expensive reference without any prestige ceiling.

## Selection bias and publication gates

The correction starts with discovery, not a bonus for obscurity. Fame and obscurity receive no points. Votes can inform the stated uncertainty treatment but are not evidence of attraction or intrinsic quality.

The earlier rotating universe contains 846 source entries, with a historical 500-entry review batch. It does not select the active combined Fragrantica 500. Stable source IDs are deduplicated; unresolved cross-platform identities remain separate. Named official-catalog entries are distinct research leads even when they share a collection URL. Counts therefore do not mean verified unique fragrances.

Research allocation rotates brand hints and uses a reproducible hash within each brand, without consulting ratings, vote counts or creator mentions. This reduces seed-order domination; it does not make the universe representative. Most inherited links still originate in five familiar seed pages and two top lists. The two newly inspected official brand catalogs add a separate discovery route, not preference evidence. The original Bois de Jasmin rating archive and inspected Iris Hermit review add a route based on published critical merit. An individual five-star assessment is retained in its original context; it is not treated as a survey or pooled into community scores. Historical reviews also require a current-edition check.

Expansion must cover full brand directories across designer, niche and affordable makers; high-rating candidates with modest exact vote counts; verified alternatives across several scent families; and dated new-release and older-release archives. Track the discovery route, source engagement count when actually observed, edition identity and eligibility. Unknown engagement is not low exposure. Review allocation can balance brands and fragrance families, but that balance must never become ranking points.

Preserve popular references for comparison. The current popularity prefix is a user-chosen acquisition boundary, not a quality score or a claim of representative market coverage. Record the candidate-selection rule before inspecting winners. Compare like questions and testing contexts within the audience and use case; an unknown-gender star average cannot replace a female on-wearer preference comparison.

The engine keeps diagnostic benchmark positions separate from overall ranks. It withholds overall rank unless the policy target is overall_quality and candidate_pool_reviewed, comparable_evidence_reviewed and sensitivity_reviewed are all explicitly true, with complete scored components. These flags attest to substantive review; they do not perform that review. Current policies remain unreviewed. A community_rating_baseline target cannot be promoted into an overall ranking by flipping review flags.

The current numeric indices still use heuristic shrinkage. Small samples can move an estimate toward its prior; that is not proof that a less-discussed fragrance is worse. Before publishing a best list, assess small-sample sensitivity and source selection separately, report support and gaps, and obtain the comparable evidence needed by the target. Do not add an automatic penalty for being popular or an automatic reward for being obscure.

## Evidence eligibility

Every quantitative observation needs an exact denominator, original source, collection timestamp with timezone, question or metric, declared scale, known or unknown audience, and independence identity. Store the result shown by the source, not a fabricated reconstruction of individual ballots.

Use original poll screenshots, tables, videos or articles where accessible. For gender-specific evidence, preserve the source of the demographic claim. Product marketing labels, creator gender, follower counts and a video's target audience do not identify voters. A title saying “women's favorite” does not itself prove that only women voted.

Separate four different questions: general scent liking, attraction to a scent on a male wearer, preference for one's own wear, and a comparison between specific scents. A blind paper-strip sniff is not a skin-wear comparison. Record age range, country, recruitment, branded or blind presentation, skin or strip, dose, dry-down time, setting, offered choices and sponsorship when disclosed. Unknown details remain unknown.

Do not convert a creator's ordinal top-ten list into invented 9.8/10 ratings. Qualitative reviews can support descriptions, conflicts and discovery without becoming numerical votes. Exclude AI-generated summaries as original evidence. A retelling of a poll is the same study, not another sample.

The engine rejects private tests, explicitly nonquantitative records, missing or rounded sample counts, invalid values, non-web evidence URLs, and gender-specific observations lacking demographic provenance. Human review is still required: schema validity cannot prove that a source is truthful.

## Audience policy

The proposed mainstream designer appeal weights are female 65%, male 20%, and mixed or unidentified community 15%. The specialist profile uses female 40%, male 40%, and community 20%. These are explicit user-aligned policy choices, not scientifically estimated population proportions.

Mainstream status does not prove ownership prevalence. Niche coverage is often uneven, but the project has not measured gender-specific ownership for these products. The specialist profile accommodates available collector evidence; it does not label collectors as male.

Within the available audience channels, weights are renormalized. Missing female evidence is not entered as zero and does not lower a score by itself. A score relying only on unknown-audience ratings is labeled indirect community evidence. It cannot be described as a demonstrated female-preference score.

The engine marks direct female support only for eligible female polls or blind comparisons explicitly about scent on a male partner. This flag establishes the presence of relevant evidence, not the representativeness or sufficiency of that evidence.

## Implemented experimental calculation

Normalize a source mean to its declared maximum, producing x in [0,1]. This simple transformation does not calibrate different platforms' scales; cross-platform comparisons remain exploratory.

For one source and metric:

```text
n_cap = min(exact source vote count, 1000)
n_effective = n_cap * quality
adjusted_mean = (n_effective * x + 20 * 0.70) / (n_effective + 20)
source_weight = quality * ln(1 + n_cap)
```

Compute each channel's weighted mean, then apply the available audience weights. For the experimental full policy, the proposed component weights are appeal 70%, longevity 20%, value 10%. Missing components are renormalized and coverage is published. Sillage is recorded, but greater loudness receives no automatic bonus.

The prior mean 0.70, strength 20, sample cap 1000, log weighting and quality multipliers are transparent heuristic settings. They are not fitted Bayesian population parameters. Votes are self-selected, may overlap across sites and are not assumed to be independent random respondents. No confidence interval is manufactured from an aggregate mean without its underlying distribution.

Latest captures replace older captures of the same source/metric/audience in scoring; earlier snapshots remain in the research archive. Comparison uses timezone-aware chronology. Source count is a count of source identities, not a number of unique people.

### First published baseline

The original report used one component and one platform: eligible Fragrantica general community appeal. All five eligible captures were designer fragrances. With every count above the same cap, the calculation gave exactly the raw star-rating order. That result could not answer which fragrances best meet the intended criteria.

The earlier pilot preserves those five reference indices and withholds overall ranks. The complete website now displays the raw community ratings for all 500 entries in the selected combined population, with a separate alternative explorer. The community means are not an overall quality ranking; broader comparative evidence remains incomplete.

The five Parfumo captures have been quarantined pending source-integrity review. Other responses had plausible titles but contradictory product details; an isolated browser attempt was then denied. No conclusions about the cause are asserted. No further requests to that source are part of this pilot.

The full appeal/performance/value policy remains a diagnostic proposal. Do not present a comparison between appeal-only and fully measured products as a validated comprehensive ranking. Price, versatility, exposure, uniqueness and formulation effects are not secretly imputed.

## Precision, support and validation

Calculate before display rounding, retain the underlying numerical score, and show three decimals. Deterministic differences can affect ordering, as in competitive ranking ladders. A 0.001 gap does not establish a perceptible or statistically reliable preference difference.

Exact numerical ties use a stable ID ordering solely for reproducibility. Do not call that a meaningful win. Single-source and cross-source labels describe support breadth; neither is a statistical confidence level.

Before a combined guide is published, compare same-platform baselines with cross-platform results, leave one source out, vary plausible priors and weights, inspect disagreement, and publish rank ranges. Those sensitivity analyses have not yet been implemented or completed in this pilot. Do not invent uncertainty bands.

If enough original paired comparisons become available, evaluate a regularized Bradley–Terry model with connected comparison groups and cluster-aware resampling. It is inappropriate to invent matchups from unrelated star ratings. The present engine is a weighted rating model; it is not LumiRank, Elo or Bradley–Terry.

Keep an independent set of actual preference comparisons for evaluating calibration and rank accuracy. Until such data exist, use “experimental community benchmark” as the report status.

## Source and poll audit

Tai's public YouTube video reports results attributed to Fragrantica annual surveys. Its headline sample claim has not been verified as unique women, and per-fragrance denominators are unavailable in the inspected description. Reported approval percentages and order also differ. The audit preserves the attributed claim without using it as a numerical input.

A Which? test describes an unbranded comparison involving more than 40 people and 14 scents. Its reported female favorite is relevant within that tested set. The exact female subgroup size and raw individual preferences are unavailable in the reviewed article, so it contributes qualitative context only. Its page also contains inconsistent dates that need resolution before longitudinal analysis.

Fragrantica's 2025 awards are a priority original source. The category title, voter eligibility, ballot mechanics, raw denominators and any account-age weighting need verification before gender-specific scoring. Access denial is not permission to substitute a derivative summary as the original dataset.

The detailed audit and exact URLs are maintained in data/evidence/source-audit.json and data/source-registry.json.

## New releases and archives

A release enters the discovery queue when an official brand page or attributable announcement establishes its identity. Database “recently added” dates are not launch dates. Store announced, launched, first observed and collected dates separately.

The proposed review cadence is discovery weekly; first evidence check around 30 days after launch; fuller reviews around 90 and 180 days; established entries quarterly; price checks at publication and whenever a buying recommendation is made. This is a maintenance policy, not an active scheduled automation.

A new release remains provisional while evidence is thin. Small samples receive the declared shrinkage; novelty and marketing spend earn no points. Publish the evidence date, policy version, source changes and reason for a rank change so a new sample is distinguishable from a changed algorithm.

Use Now Smell This archives for announcements and chronology, official brand pages for identity, accessible source versions for historical claims, and original reviewer posts for dated commentary. Respect noarchive directives; retain permitted factual extracts, hashes and URLs rather than copying full reviews or uploading restricted pages to public archives.

When a source returns a challenge, 401, 403 or 429, stop the affected host and preserve the last good data. Honor Retry-After when present; otherwise the implemented 429 cooldown is six hours. Authorization and integrity holds require manual review. Do not rotate proxies, accounts or hosts to bypass access controls.

Private sampling after buying can help the user decide what to wear. It remains outside this algorithm.

## Selective alternative research

Start with references inside the combined 500. An alternative can qualify through faithful similarity, a supported improvement, or a worthwhile tradeoff. A lower aggregate rating does not automatically disqualify a faithful or compelling-value option. User-named examples change research priority, never merit points or population boundaries.

The cached screening pass requires a reported alternative rating of at least 4/5 with 300 exact rating votes, at least 100 similarity votes, at least 70% agreement, and no provider-marked relationship dispute. It then requires at least one signal: 85% similarity agreement; a paired aggregate rating gap of at least 0.10/5; or at least 75% similarity agreement plus a reported alternative high price no more than half the reference low price. These are transparent allocation thresholds, not a fitted definition of goodness. They can miss excellent low-volume releases, which remain eligible for separate evidence review.

Similarity agreement is yes / (yes + no), not a measured percentage of formula identity. A rating gap compares different self-selected voting populations. Price ranges without verified bottle volumes establish only an apparent price tradeoff. No signal on its own proves superiority. Supporting and critical original comparisons must be reviewed before a recommendation claims better performance, identical smell or verified value.

The secondary source contributes 404 mapped relationships to references in the current population. Four lack comparable rating pairs; 232 of the remaining 400 pass this screen. These counts describe cached coverage, not complete research on all similarity neighbors. Neither a research candidate nor a requested example receives an overall rank.

Keep secondary-provider acquisition, indexed primary-page excerpts and direct native captures distinct. The user's screenshot corroborates the visible ten-position prefix; the complete 500-position native list remains independently unverified. Private purchases and wear testing stay outside the calculation.
