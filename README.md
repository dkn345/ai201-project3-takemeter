## Community
The community I chose was r/AssassinsCreed since that is the game I have been playing lately. It is a third person series with many games each of which take in different places and time periods. The overarching idea is Templars vs Assassins where Templars seek peace via force while Assassins, free will.

## Labels
 "analysis":  0,  #If a post contains concrete game facts, mechanics, or lore details to explain how or why something works, it must be classified as Analysis—even if the user uses casual framing (like "I think") or expresses frustration. The presence of objective, explainable game evidence overrides subjective language.
    - Assassin's coin glitch in liberation help
    - How were you able to get to the coin npc while in the slave persona? There's 3 coins in the bayou, 7 in New Orleans.  
 "opinion":  1,   #If a post makes an overarching value judgment (e.g., "the game is bad," "the DNA is gone," "it's boring") and only uses vague generalizations rather than specific,  game data/mechanics to back it up, it must be classified as Opinion. If a post is structured entirely around a personal wish list or emotional vent, it remains an Opinion even if it mentions a mechanic. Even if they use specific game mechanics to back up their point, if the core purpose of mentioning the mechanic is to critique, praise, or complain about game design rather than to inform or help others, it remains an Opinion
    - First time exploring the villa as Desmond. Love the music and the scenery, and playing as Desmond like an assassin was so fun
    - I like all the homestead missions for assassins creed 3. It really made the game feel more personal for me

## Data Collection Plan
I will go on r/Assassins Creed reddit and filter the posts through tips or queries asking for opinions. Based on that I will click on the post and pick comments and categorize. In terms of edge cases, if something is leaning more lore or gameplay analysis and is not as biased, I would pick analysis. If the post sounds more opinionated such as emphasizing why they don't like a component, I will say it is opinion.

## Labeling Process
I tried to filter through searching terms like tips/tricks or lore details. I also look at reception since those helped me filter the such as how the first game was received which helped me curate the opinion portions.

## Label Distribution
Label distribution:
label
opinion     103
analysis     97

## Difficult to label
"Petruccio would take Claudia's place as the more business minded member of the family when he grows up, since he can't do anything physical." I initially thought it was analysis however in the definition I made speculative or what-if scenarios under opinion since we don't know how the story would go and we can just guess.

"For me it’s harder than brotherhood, especially trying to get 100 percent sync. Definitely on memory sequence 6 when you are SOMEHOW not supposed to take any damage despite there being 100 guards! Don’t get me wrong other than the 100% sync I love this game and its story and happy to have the chance to play as Altair but I just can’t stand it. It was far more enjoyable and relaxing when I could just play brotherhood. I’ve nearly 100 percent that entire game. I am frustrated to the point I’m about to quit this game, it just seems so unfair with the amount of guards that come after you." I also thought this was analysis since I was debating with Gemini to clarify whether it was opinion or not. This had stats and some gameplay but overall it read as opinion since a lot of the focus is on what the player likes or dislikes.

""Edit: Added some historical context. One bag of rice back then had a purchasing power of about 700 to 1,000 USD today.

As an old fan of this series, I really hope Assassin's Creed can have a good future. I tried my best to understand this game and ignore some negative comments about Shadows, but there are some details that make me feel a little confused.

In the game, we can see these rice bags left everywhere carelessly. They are placed beside the roads, or even right in the middle of the roads. We can also see them in wide open spaces, and in the messy corners of bandit camps. There is no proper storage and no cover for them, so they just stay under the sun and the rain.

For Asian people, rice is not just food to fill our stomachs, but it is also a very important soul that connects our family emotions, our culture, and our history. Americans might not eat bread every day, and Italians might not eat pizza every day, but we really eat rice every single day.

Therefore, leaving these rice bags everywhere. And they have no cover, so they stay under the sun and rain, which makes the rice become useless garbage. Seeing rice bags randomly placed anywhere under the rain makes me feel a little sad.

More importantly, in the Japanese Sengoku period, ""rice"" was actually the salary for samurai. Their income was calculated by how much rice they received. Those are not ordinary sacks, but standardized rice bales called *kome-dawara*. They held a defined quantity of rice with clear economic value and were used for taxation, stipends, and trade. They usually contained brown rice. At the time, rice was a major tax resource, military supply, and the basis of samurai stipends. Leaving rice bales like that would expose important food and valuable property to moisture, fire, theft, or damage.

r/assassinscreed - According to the official Nagano Inavalley Tourism Bureau
According to the official Nagano Inavalley Tourism Bureau
For example, Yasuke’s master, Oda Nobunaga, his historical income was ""7 million Koku"", which is about 1 billion kilograms of white rice. If Nobunaga gave Yasuke his salary, it would also be rice.

I cannot help but wonder, does UBI maybe not know that those are bags for valuable food? Is it possible that the management gave the studio these texture assets, but the staff did not recognize what they were, so they just pasted them to fill the empty space?

Also, perhaps for the light and shadow system, there are too many lighting facilities, like many bonfires, torches, and lamp stands.

At that time, almost all buildings were made of wood, so this looks very dangerous. Torches are even placed right next to straw and rice bags.

Even if I try not to worry about these things, seeing lamps lighted outdoors in the broad daylight is still a bit strange for me. I really hope the development team can notice these small details."' Gemini thought it was opinion but I felt like it was more analysis because of the amount of research and detail therefore I decided it was analysis.

## Fine tuning approach
For the fine-tuned model, I used distilbert-base-uncased from Hugging Face with a sequence classification head. My dataset had 200 total labeled examples, split into 140 training examples, 30 validation examples, and 30 test examples. The labels were analysis and opinion.

I used the notebook’s default training setup: learning rate 2e-5, batch size 16, weight decay 0.01, and 3 training epochs. I also experimented with increasing the number of epochs to 4 and 5 to see whether additional passes through the training data would improve performance. Validation accuracy peaked early, so additional epochs did not clearly improve performance and increased the risk of overfitting on the small dataset. Because of that, I kept the default 3-epoch setup.

## Baseline

## Evaluation
Overall: ==================================================
         RESULTS COMPARISON
         ==================================================
         Model                               Accuracy
         ---------------------------------------------
         Zero-shot baseline (Groq)              0.833
         Fine-tuned DistilBERT                  0.833
         ---------------------------------------------

         Fine-tuning improvement: 0.000

Baseline accuracy: 0.833  (evaluated on 30/30 parseable responses)
Per-class metrics (baseline):
              precision    recall  f1-score   support

    analysis       1.00      0.67      0.80        15
     opinion       0.75      1.00      0.86        15

    accuracy                           0.83        30
   macro avg       0.88      0.83      0.83        30
weighted avg       0.88      0.83      0.83        30

Fine-tuned model accuracy: 0.833
Per-class metrics (fine-tuned model):
              precision    recall  f1-score   support

    analysis       0.86      0.80      0.83        15
     opinion       0.81      0.87      0.84        15

    accuracy                           0.83        30
   macro avg       0.83      0.83      0.83        30
weighted avg       0.83      0.83      0.83        30

| Actual \ Predicted | Analysis | Opinion |
|-------------------|----------|----------|
| Analysis          | 12       | 3        |
| Opinion           | 2        | 13       |

Wrong predictions:
--- #1 ---
Text:      I played the first three games when they came out and I liked them, but after that, most of the titles always lost me after a couple of hours. The constant bugs didn’t help either (I’m looking at you),...
True:      analysis
Predicted: opinion 
I think the model believed this was an opinion because of the personal aspects such as I liked them or it lost me. However, I labelled it analysis because of the fact that the post gave tips such as turning HUD off and how to reduce clutter which felt more like a guide than opinion so I put it as analysis.

--- #2 ---
Text:      
Yeah, I got really confused to after changing my TV to an HDR one. Thankfully it's just a matter of turning the HDR off and then on again on the console settings. But really, this remaster was rathe...
True:      analysis
Predicted: opinion 
The model likely focused on the emotional language at the beginning of the post, such as 'I got really confused,' while I labeled it as analysis because the primary purpose of the comment was to provide a troubleshooting solution.

--- #3 ---
Text:      
Altaïr Ibn-La’Ahad is the greatest assassin. He is the assassin from the first game. He saved the assassin order from being destroyed by Al-Mualim, and was able to see past his lies and even withstan...
True:      opinion
Predicted: analysis
Although the text has true points, I leaned more towards opinion because the question itself was asking opinions on who the greatest assasin was. This example demonstrates the main challenge in my dataset: users often support opinions with lore evidence, making the boundary between analysis and opinion difficult

Sample:
============================================================
POST:
Assassin's coin glitch in liberation help

PREDICTION: opinion
CONFIDENCE: 0.512
============================================================
POST:
Templars hunt for the tools to bend people's will under a guise of "order" while pretending like every agent of control will be good-willed. And that's ignoring that Templars were behind Hitler's rise and gave him apple to make a world order. Assassi

PREDICTION: opinion
CONFIDENCE: 0.501
============================================================
POST:
I thoroughly enjoyed AC1 when I first completely played it on PC during the pandemic 6 years ago and then played it again in 2023 on the 360. What I didn't know was the notes of Altair in 1. I knew about the writings of Altair in AC2 in the codex. Yo

PREDICTION: opinion
CONFIDENCE: 0.501
============================================================
POST:
Mine is similar to yours

       Story is far more cinematic and missions are pretty cool too

       General gameplay is worse all around to me.

PREDICTION: analysis
CONFIDENCE: 0.507
============================================================
POST:
don't think so.

        For me, the problem was the lack of coherence between stories and the super slow pace. There were a lot of activities, but I didn't find they were well organised.

        It has been years since I played and I never returned

PREDICTION: opinion
CONFIDENCE: 0.513


POST:
I thoroughly enjoyed AC1 when I first completely played it on PC during the pandemic 6 years ago and then played it again in 2023 on the 360. What I didn't know was the notes of Altair in 1. I knew about the writings of Altair in AC2 in the codex. Yo

PREDICTION: opinion
CONFIDENCE: 0.501
This one is correct as it is clearly opiniated and the model predicted it correctly. This is reading as personal which the model got correctly.

## Reflection
I intended the model to learn the difference between posts that primarily inform or explain and posts that primarily express opinions, preferences, criticism, or speculation. Overall, the model captured this distinction reasonably well. It correctly learned that troubleshooting posts, lore explanations, gameplay guides, and factual mechanic discussions usually fit the `analysis` label, while rankings, praise, complaints, and wishlist-style posts usually fit the `opinion` label. The main gap was that many Reddit posts mix both styles. A user might make a personal claim and then support it with detailed lore or gameplay evidence, or they might give useful advice while also sounding frustrated. The model sometimes focused on surface wording instead of the post’s primary purpose. For example, emotional phrases like “I got confused” or “I liked them” pushed some analysis posts toward `opinion`, while opinion posts with lots of lore evidence were sometimes predicted as `analysis`. This suggests the model learned useful patterns, but it did not always fully capture the deeper intent behind a post. To improve the classifier, I would collect more edge cases where users combine opinionated wording with evidence-based explanation. I would also tighten the label definitions further by emphasizing that the final label should depend on the post’s main purpose, not just whether it contains facts or emotional language.

## Spec Reflection
In terms of spec, I really liked how I was supposed to try to make boundaries clearer. It was difficult to find the difference but I liked the aspect of understanding where I was supposed to put such as what constitutes as analysis vs an opinion. I actually did not deviate much except for modifications of definitions as I was going through reddit.

## AI Usage
I used AI tools in several parts of this project. First, I used Gemini to stress-test my label definitions. I gave it my definitions for `analysis` and `opinion` and asked it to generate boundary examples that would be difficult to classify. Some of those examples showed that my original definitions were too broad, so I refined my rules to focus more on the primary purpose of the post. Second, I used ChatGPT during annotation to discuss difficult examples. I did not use it to blindly label the dataset. Instead, I compared its suggestions against my own label definitions and made the final decision myself. This helped me stay consistent when posts included both factual explanation and subjective language. Third, after evaluation, I used ChatGPT to identify patterns in the model’s wrong predictions. It pointed out that most errors involved posts that mixed personal opinion with evidence-based discussion. I verified this pattern myself by rereading the misclassified examples and included it in my error analysis.


