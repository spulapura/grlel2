Mahowald et al (2012)

1. Background
	1. Zipf-- maximize efficiency by using shorter encodings for frequently occurring messages (ie most frequent words are shorter)
		1. Chomsky did not like...
	2. Additional hypothesis-- not just a function of word frequency, but rather word surprisal (use longer forms when needing to convey more information)
		1. i.e. words that are predictable from context are shorter and have low surprisal, words that are unpredictable from context are longer and have high surprisal
	3. New insight of this paper-- content words (not just phonological, contraction, function words) are also sensitive to UID
		1. Controls for syntactic category
2. Corpus study
	1. Unsmoothed trigram model to estimate average surprisal for each pair
	2. Mean surprisal was higher for the longer form 
	3. Even when controlling for overall frequency in a regression-- even when there was no difference in frequency, the discrepancy in surprisal held
3. Behavioral study
	1. Asked the participants to choose their preferred completion in a supportive context and neutral context
		1. Verified that indeed without the options, the participants chose the expected word(s) in the supportive context but not the neutral context, suggesting that the former is a low suprisal/information context
		2. And never included the key word in a common phrase
	2. Results-- short form was chosen more often in the supportive context than in the neutral context, long form was chosen more often in the neutral context than the supportive
4. Discussion
	1. Overall, corpus study and behavioral study seem to be in agreement that short forms are preferred in low-information contexts
		1. Despite inherent flaws in n-gram models
	2. Behavioral study also helps rule out learning specific constructions where shorter forms are preferred
	3. In context word length predictability not explained by random typing
	4. Can we predict lexical change over time?

Jaeger (2010)

1. Background
	1. UID-- preference to uniformly distribute information across a linguistic signal
	2. Testing in the case of syntactic reduction-- that complementizer, comparing against competing theories to explain that phenomenon (availability, ambiguity avoidance, dependency processing)
	3. Overarching result is that production is probability sensitive
	4. Less information in context = more redundant
	5. Speakers manage information density to avoid peaks and troughs-- observe this at choice points
	6. Model as a limited bandwidth noisy channel, transmit information uniformly close to capacity
		1. Not perfectly optimal-- natural language has other restrictions (ie has to be learnable)
		2. But still efficient
	7. Information *density* -> information per unit of time (ie bitrate)-- this study doesn't account for articulatory detail
	8. Speakers have access to probability distributions over linguistic units
	9. Corpus study -> don't want to skew the results by priming the participants to biased distributions
2. Experiment design
	1. Basic idea is "that" complementizer reduces the information density all else being equal
	2. So when the CC is predictable, we expect no "that" and when it's less predictable, we expect explicit complementizer
	3. Estimate conditional prob of CC given context as P(CC|matrix verb lemma)
	4. So higher probability for words like "think" (which usually have a CC) vs words like "confirm" (which often don't)
3. Data/procedure
	1. Annotated and manually verified PTB corpus
	2. Chose cases where the lemma occurred frequently enough to be representative, and when they were able to annotate for the control variables
	3. Control for 25 different other variables
	4. Added random speaker intercept
	5. Found low correlation between information density and the control parameters
4. Controls
	1. Production pressures -> use the complementizer to prevent disfluency/ when the continuation is not readily available
	2. Temporary ambiguity -> ie remove "that" if it's ambiguous whether you mean it as the direct object or a complementizer during comprehension time
	3. Dependency processing, especially when the CC starts farther from the matrix verb
		1. length(matrix verb to CC)
		2. length(CC onset)
		3. length(CC remainder)
		4. position(matrix verb)-- production difficulty differs depending on where you are in the sentence
	4. Ambiguity of the onset of the CC
5. Results/discussion
	1. Speakers distribute information uniformly across utterances (unless there's a clash with other constraints)
	2. Higher preference for complementizer that when there's higher information density at the complement clause onset
		1. Even after controlling for various other parameters which also affect this 
	3. Implications -> syntactic production is probability sensitive (choices during online production are affected by probability)
		1. Most other accounts of syntactic production do not consider language production to be probability sensitive
	4. Not as strong as rational cognition -> efficiency rather than optimality, have to consider other constraints like learnability
	