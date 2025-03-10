
Rubio-Fernandez (2016)

- Sometimes explicit color references facilitate object ID even if they're not strictly necessary
Introduction
- Noncontrastive use of color -> is it redundant?
- Seems like a violation of Quantity (more info than necessary)
- Color more often than other adjectives like size
- Speaker vs Listener
	- Speaker -> don't have to search for other utterances/determine if the adjective is necessary
	- But that also benefits the hearer (otherwise wouldn't have consideration for if the given info is enough)
	- Does it make a huge difference? Generally speaker and hearer will be coordinated in which information is useful
	- collaborative process
- Efficiency vs Informativeness
	- For example, if cup and blue cup are both equally informative wrt the scene, blue cup might be more efficient because it'll help you ID the object faster
	- Especially if there's not a lot of other blue objects
- Factors involved -> RCS more efficient if the referent is the only object of its color, more efficient in prenominal position (since you can eliminate some objects ahead of time), semantic constraints (ie if the referent has lots of color variability, if it's an atypical color, if color is more central to the object than other properties)

Experiment 1:
- Paper dolls wearing clothes all same color or all different colors
- More RCAs in polychrome displays vs monochrome -> yes, for both languages
- More RCAs in English than Spanish -> yes, for both types of display
- Regarding semantic category, RCAs used frequently in general since color is a central property of clothes (in comparison to a previous example using shapes)
	- So we can say that RCAs were driven by semantic category, since all other conditions were the same (monochrome, language) vs the other experiment

Experiment 2:
- Studying typicality -> 2 possible explanations, ie specifying the pink banana because it's highly salient/surprising, or specifying it so that the listener doesn't just hear banana and look for a yellow one
- Manipulation -> told the participants that prior participants had failed to communicate the object adequately. So we expect more RCAs in the atypical color trials
- Atypical > Variable > Typical was the ranking of RCAs used
- More RCAs in the atypical condition when given cautionary instructions (instruction type wasn't significant for other typicality conditions)
- Perhaps some confounds from when a variable/typical trial comes after an atypical trial (tended to use them in subsequent trials more often than in trials that followed another typical/variable)
- Normed for salience
- Provides evidence for cooperativity of RCAs -> since only the atypical ones went up in the cautionary condition, shows that speaker is aware of what might cause the communication breakdown and adjust


Degen et al, 2020

- Key idea is changing the informativeness computation from wrt boolean semantics to continuous semantics, which changes how useful different types of redundant expressions are
- RSA model -> tradeoff between cost and information for boundedly rational agents

Background
- People use the color when not necessary
- People use base level reference when superordinate reference would suffice
	- Alternative accounts -> salience, base level preference
- Asymmetry between color and size, more redundant with more scene variation, more redundant with atypical features
- Nominal reference -> People prefer base level, sometimes subordinate when the referent is atypical for the base level
- Basic RSA -> computes literal listener probabilities according to boolean semantics, so basically you get 1 if it verifies and 0 if not. So blue banana and banana are equally informative if there's only one banana and it's blue. 
	- RSA parameters -> softmax temperature (0 is random, 1 is softmax, infinity is maximizing). Also a cost parameter
	- Can extend to two word utterances which just expands the lexicon
	- But cost alone can't explain why blue banana is better than banana
- Continuous semantics RSA -> rather than just 1 if it's in the extension and 0 if it's not, we instead do $x_s$ if it's in the extension and $1-x_s$ if not. 
	- Pick a bigger value for color, since color has less variability of interpretation
	- So then we get the effect of redundancy helping when color is a distinguishing dimension, but not when size is a distinguishing dimension
	- **** Redundant references are useful when when the redundant dimension is less noisy than the sufficient dimension
- Scene variation -> added another $x_t$ encodes noise in the noun
	- If type variability is less than color variability, don't need the redundant color
	- Usually size variability will be much more than color variability so less of this effect when size is the additional factor

Experiment 1 -> Size vs Color
- varied number of distractors (total) and (sharing the redundant feature)
- Effect of sufficient property -> more often used color redundantly than size redundantly
- Effect of scene variation -> redundant adjective increased with variation
- Interaction between sufficient property and scene variation -> scene variation effect smaller when color-sufficient rather than size-sufficient
- Evaluation of the model shows semantic value of color higher than size, as expected
- No effect of cost
- Relative vs absolute adjectives, color is less subjective, incrementality, saliency
- Improves on existing models which only consider distinguishing features or order features in a certain way

Experiment 2 -> Typicality
- Previous experiment's model doesn't distinguish between red and mauve, or between blue banana and yellow banana
- Redefined semantics such that yellow verifies with banana with high probability, and blue verifies with banana with a low probability
- So there's a much greater gain when you say blue banana vs banana, when the banana is blue
- Manipulated color typicality, held size constant now
- Empirically elicit typicality values -> how does it compose with the modifier type noise?
- Conditions -> informative, informative-cc, overinformative, overinformative-cc (color competitor)
- Large typicality effect on overinformative conditions, less so in informative conditions
- Effect of typicality -> more typical was lower likelihood of color mention, even when color was necessary to establish the reference (ie banana is enough if the other banana is blue)
- Effect of informativeness -> color reference less likely when overinformative than when informative
- Effect of color competitor presence -> more likely when competitor was absent
- Best model was fixed + empirical, with no cost term (so with the empirical typicality plus what we got in experiment 1 for type level semantics), $\beta$ interpolates
	- Still found no need for the cost function, even when taking frequencies into consideration
- Some surprises -> color+type underpredicted in informative context, and overpredicted in overinformative context 

Experiment 3: Taxonomic Level, Unmodified Referring Expressions
 - subordinate, base, superordinate level reference
 - Same setup as 2, but with distractors either matching or not matching the target in base or superordinate category
 - Predict that the subordinate term is useful when the object is typical of the subordinate category but atypical of the base category (ie penguin vs bird)
 - Categories -> subordinate necessary, base sufficient, super sufficient 
 - Results
	 - Sub level only preferred when necessary to distinguish
	 - Even in these cases there was a preference for base level
	 - Sub level goes up when object is typical of sub level
	 - Sub level most likely in sub necessary, then base necessary, then super sufficient
	 - Typicality -> sub preferred more when typical of sub and atypical of base
	 - Length -> sub dispreferred when longer than base
	 - Domain -> some domains have a base level preference, some (candy) the sub is preferred, some (furniture) the super is fine
	 - Frequency didn't affect sub level mention
 - Empirically skewed beta preferred over the fixed one
	 - 
