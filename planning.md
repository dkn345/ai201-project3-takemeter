## Community
The community I chose was r/AssassinsCreed since that is the game I have been playing lately. It is a third person series with many games each of which take in different places and time periods. The overarching idea is Templars vs Assassins where Templars seek peace via force while Assassins, free will.

## Labels
 "analysis":  0,  #If a post contains concrete game facts, mechanics, or lore details to explain how or why something works, it must be classified as Analysis—even if the user uses casual framing (like "I think") or expresses frustration. The presence of objective, explainable game evidence overrides subjective language.
    - Assassin's coin glitch in liberation help
    - How were you able to get to the coin npc while in the slave persona? There's 3 coins in the bayou, 7 in New Orleans.  
 "opinion":  1,   #If a post makes an overarching value judgment (e.g., "the game is bad," "the DNA is gone," "it's boring") and only uses vague generalizations rather than specific,  game data/mechanics to back it up, it must be classified as Opinion. If a post is structured entirely around a personal wish list or emotional vent, it remains an Opinion even if it mentions a mechanic. Even if they use specific game mechanics to back up their point, if the core purpose of mentioning the mechanic is to critique, praise, or complain about game design rather than to inform or help others, it remains an Opinion
    - First time exploring the villa as Desmond. Love the music and the scenery, and playing as Desmond like an assassin was so fun
    - I like all the homestead missions for assassins creed 3. It really made the game feel more personal for me 

## Hard Edge Cases
I must say I dont think there is much DNA in AC anymore as the games all have such widely different gameplay, story and aesthetic designs. The closest thing is the historical setting.
    - This looked like analysis since it is true that each game has different gameplay and storylines however the way the user worded it seems like opinion since they said "I dont think." The label is opinion for this one.
It’s hard to get a clear why. But the colonial assassins clearly violate every tenet of the creed. Which is funny because this is what causes their downfall, they don’t hide in plain sight and put their flag up huge to show where they are, they don’t care if they kill innocents and they compromise the brotherhood constantly.
    - The subjective language of "hard to get a clear why" made me think this was an opinion. However, a lot of explanation of what the assassins do is here, so the label is analysis for this one. 

## Data Collection Plan
I will go on r/Assassins Creed reddit and filter the posts through tips or queries asking for opinions. Based on that I will click on the post and pick comments and categorize. In terms of edge cases, if something is leaning more lore or gameplay analysis and is not as biased, I would pick analysis. If the post sounds more opinionated such as emphasizing why they don't like a component, I will say it is opinion.
    
## Evaluation Metrics
I will use accuracy, precision, recall, F1-score, and confusion matrix to evaluate my model. Accuracy measures overall performance, but it does not show whether the model performs well on both labels. Precision measures how often a predicted label is correct, recall measures how many examples of a label are correctly identified, and F1-score balances both precision and recall. The confusion matrix helps visualize which labels are most frequently confused with one another, making it easier to identify weaknesses in the classifier and improve the label definitions if necessary. These metrics are important because a model could achieve high accuracy by overpredicting one label while performing poorly on the other.

## Definition of Success
I would consider the classifier successful if it achieves at least 75% accuracy on the test set and performs consistently across both labels. A useful classifier should be able to distinguish informative posts from discussion-oriented posts most of the time. For deployment in a real community tool, I would consider performance above 80% accuracy with balanced precision and recall to be good enough.

 ## Why it matters
These distinctions matter because they help separate informative content from discussion-oriented content. Analysis posts are useful for players looking to learn mechanics, solve technical issues, or understand the games better, while opinion posts allow community members to share perspectives, criticism, preferences, and ideas about the franchise.

## AI Tool Planning
I will ask Gemini to generate 5-10 posts that sit at boundary of my labels. I will check whether it can be clearly classified based on my descriptions. 
When I come across ones that are between the boundary of analysis or opinion, I will ask ChatGPT to look and label and decide if I agree or not. 
I might also ask ChatGPT to help with failure analysis especially after evaluation so I can identify common patterns in the model's mistakes and determine whether the issue comes from the labels, the dataset, or the model.


