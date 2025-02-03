
**Implicitness of Discourse Relations (Asr and Demberg, 2012)**

Background
- Discourse relation -> inference to establish coherence between sentences
- Propositional arguments and connective operator (which could be explicit or implicit)
- Expect to omit the connective operator in high probability context (ie implicitness correlates with high probability/predictable discourse relations)
- Continuity Hypothesis -> continuous discourse is easier to process/more predictable than discontinuous discourse (ie same frame of reference/perspective)
	- Prior studies: adversative (ie discontinuous) connectives let to processing disruption when misused, no such effect for missing additives or causals
	- And correctly placed adversatives are more beneficial for processing -> more salient than continuity connectives
	- Concession (effect before cause) should be more salient than forward causals
- Causality by default hypothesis -> prefer causal inference over other types when establishing coherence
	- EEG studies show causal relations even without connectives are easier to process
	- Subjects prefer causal relations when choosing discourse continuations with no given connective
	- To the contrary -> participants answer why? questions based on causal inference reliably only when explicit "because" connective was included
- Penn Discourse Treebank -> instead of small experimental vignettes, use natural text
	- Annotates explicit and implicit discourse relations (when implicit, inserted by annotator) with a connector  and 2 propositional arguments
	- Four classes -> contingency, comparison, temporal, expansion
	- Temporal can be synchronous and asynchronous (precedence and succession). 
		- Asynchronous -> discontinuous, but should be easier to process when in forward temporal order
		- Synchronous -> ambiguous continuity (sometimes introduce new events)
	- Contingency can be reason (forward) or result (backward) cause/consequence relations
		- Pragmatic cause -> justification for epistemic causal relationship
		- Conditionals also in PTB but not in study (can't classify as causal or continuous/discontinuous)
	- Comparisons -> all discontinuous
		- Expectation and contra-expectation negative-causals (reason and result)
		- Incredibly irony of this section is that it took me like 3x as long to understand these examples because they said "expectation and contra-expectation" and "reason and result" but then the first example was contra-expectation/result and the second example was expectation/reason
	- Expansions -> instantiation, restatement, list (continuous) and conjunction (often discontinuous when arg2 introduces deictic shift)
- In terms of UID, we expect
	- Continuous relations should be more implicit than discontinuous
	- Causal relations should be more implicit than other types
	- Forward temporality should be more implicit than backward
	- Backwards causals with implicit causality verbs (like "scolded") are more implicit than other backwards causals
Methods
- $$Implicitness(relation) = \frac{\# \text{of implicit } relation}{\#relation}$$
- High implicitness corresponds to high predictability
- Expected high implicitness for continuous and causal re: 2 hypotheses
Results
- By explicitness: conjunction, contrast, cause, asynchrony in that order
- By implicitness: cause, conjunction, restatement, contrast
- Conjunction, cause, and contrast are the most common relations overall, but conjunction and contrast have low implicitness
- re: Continuity Hypothesis: All the continuous categories had higher than average implicitness, and all the discontinuous categories had lower than average implicitness
- re: Causality by Default Hypothesis: not the only frequently implicit relation, but significantly more implicit than the other above-average relations
	- Supports hypothesis that causality is inferred absent explicit marker
- Temporal continuity -> in all pairs of forward/backward relations, the forward one was more implicit
- Textual order -> in explicit relations, can have arg1-connective-arg2 OR connective-arg2-arg1
	- More likely to see the latter for backwards relations, to preserve the textual temporality
	- Ie "because X, Y" rather than "Y because X" (more often than choosing "So Y, X" over "X, so Y")
- Implicit Causality Verbs -> previous evidence that listeners expect a reason after an IC verb more than after a transfer of possession verb
	- IC verbs are in reason relations significantly more often than other verbs
	- However, implicitness was actually below average for IC verbs overall, even after removing noise from semantic ambiguity, calls for further study
- Conclusions -> support for both original hypotheses, IC often in reason relations but not more implicit
	- Future work -> explaining why we expect continuous/causal relations




**Predictable Words are More Likely to be Omitted in Fragments (Lemke et al, 2021)**

Background
- Can UID explain why we use fragments, and which words we omit in fragments?
- 2 main contributions -> extralinguistic predictability effects, content word omission, not just function words (although cf. Mahowald 2012 from last week?)
- Prior accounts -> generally focusing on theoretical syntactic derivations
	- wrt Information theory -> givenness vs focus (focus must be realized)
	- But doesn't tell us why we don't use fragments when grammatically available
	- Information theoretic + game theoretic -> tradeoff of cost and risk of not being understood (cost is function of utterance length, doesn't consider other reasons for production effort)
- Main hypotheses
	- Predictable utterances are more frequently reduced
	- Predictable words are omitted in fragments
		- Avoid local minima by omitting highly predictable words
		- Avoid local maxima by ensuring that words *preceding* highly unpredictable words are realized (i.e. "where is" reduces surprisal for "the nearest ATM" in a context where asking for directions to something isn't necessarily the most likely interpretation)
	- Following UID hypothesis, generally optimizing so  bitrate approaches but doesn't exceed channel capacity, which is taken to be upper bound on cognitive resources
	- $-\log_2{p(word|context)}$
- Some difficulties in testing these hypotheses
	- Not clear what has been omitted in the fragments
	- Need to establish extralinguistic context since fragments often occur discourse initially
	- Circularity issue -> predictable words are omitted, so then their probability seems low in the dataset just by counting frequencies
Methods
- Data Processing
	- Script-based stories allows for controlling extralinguistic context -> expect the context to prime expectations about the continuation of the event chain
		- Asked for complete sentences, but subjects provided fragments anyways... so used data for surprisal estimation and analysis (confirmed that omissions weren't significantly different for "utterance" vs 
	- Annotate for prepositions articles etc, then removed function words  (i.e. don't want to predict removal of required function word in logreg, and want to preserve its information)
	- Pool "synonyms" ie refer to the same thing in this script context so we don't split the probability mass across too many features
	- Remove optional words (i.e. only want words whose absence means they've been omitted)
	- Resolve reference and reconstruct ellipsis (with minimal requirement for full sentence)
- Surprisal metrics
	- Unigram -> unigram MLE with Good-Turing gives us surprisal given extralinguistic content (ie unigrams -> no context window)
		- $S(w_i) = -\log_2{p(w_i|context_{extraling})}$
	- Context dependent -> Can't use higher order n-grams or embeddings because of circularity issue
		- $S(pour|onset) = \log_2{\frac{\alpha_{onset}}{\alpha_{pour}}}$
		- Get the probabilities of all the complete structures, then determine which parses are ruled out by the given token (i.e. the context)
		- For words beyond the onset: find total probability mass of parses that contain pot.GOAL somewhere after pour (i.e. not ruled out by pour)
		- $S(pot.\text{GOAL}|pour) = \log_2{\frac{\alpha_{pour}}{\alpha_{pot.\text{GOAL}}}}$
	- Surprisal reduction -> how much does the given word reduce the surprisal of the next word
		- $S_{reduction}(w_i, w_{i+1}) = \log_2{\frac{\alpha_{i+1}}{\alpha_{i,i+1}}}$
		- Ratio between prefix probability of i+1th word if ith word has and hasn't been included
Results
- In general, some scripts had a much lower omission rate across the board -> if only a few words fit the situation, all words have a much higher probability/more predictable
	- Found correlation between Shannon entropy and omission rate
- Logistic regression -> 3 permutations, showing high correlation between predictors (especially context-dependent surprisal)
	- Realized words have higher unigram and context dependent surprisal (unigram more so, which is opposite of what might be expected, but might be because many words were assigned context-dependent surprisal of 0 )
	- Question... why not do some smoothing on the context-dependent surprisal?
		- They do note that an actual speaker would reserve some probability mass to utterances not in the dataset, which seems like a candidate for smoothing ...
	- Surprisal reduction also predicted words to be more realized (with low correlation to the unigram predictor)
Discussion
- As predicted, speakers omit more predictable words and realize words that reduce surprisal of next word even when they could be grammatically omitted
	- Question -> longer forward context window?
- Comparison with other theories 
	- Availability accounts capture insertion before unpredictable words, but not omission of predictable words
	- Other way around for source coding (Zipfian) accounts
	- Game-theoretic accounts don't upper bound the information density (hard to compare without better way of enumerating the alternatives
- Other general results -> extralinguistic effects on probabilities, reduced importance of context? (or methodological improvement needed)