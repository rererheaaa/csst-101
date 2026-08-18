# CSST101 - BASIC MACHINE LEARNING

**NAME:** RHEA CARLIZETTE T. ABILLONAR
**SUBMITTED TO:** SIR MARK BERNARDINO
**SECTION:** BSCS - 3B

---

# Performance Task 1: From Data to Prediction - Analyzing Real-World Machine Learning Applications

## 1. Title
The Algorithm Behind Your Scroll: Machine Learning in Content and Video Recommendation Systems

## 2. Chosen ML Application
Content/Video Recommendations, specifically, the systems used by streaming video platforms (e.g, Youtube, TikTok, Netflix, Instagram) to suggest what a user should watch next.

## 3. Problem Description
Video platforms have millions of videos. No one can browse all of them manually. The problem is that it is simple to say but hard to solve. Given one user and a huge library of videos, how does a platform pick the few videos that user will most likely to watch, enjoy, and stay engaged with? Actually, there is no single correct answer. Different users like different things. Even the same user's taste changes depending on the moment. Someone binge-watching mukbang videos on a Friday night might want to do something totally different on a Saturday morning. As a Machine Learning Engineer, my task is to build a system that predicts which videos a specific user is likely to want to watch next. It does this by looking at patterns from how that user, and users like them, have behaved before.

## 4. Input and Output Identification

**Input:**
- Watch History - which videos the user has previously watched
- Engagement Signals - percentage of each video completed, likes, shares, comments, skips
- Search queries and browsing behavior on the platform
- Video metadata - genre/category, tags, length, upload, data, creator
- Contextual data - time of day, device type, day of week

**Output:**
- A rank list of videos the user is likely to watch next

## 5. Traditional Programming vs. Machine Learning
In a traditional programming approach, an engineer writes exact rules by hand, like "If a user watched a K-pop video, recommend other K-pop videos." This doesn't work well. It can't handle millions of users and videos. It can't notice small differences in taste, like a user who likes girl groups but not boy groups. And every time viewing trends change, someone has to rewrite the rules. Meanwhile, in a machine learning approach, the engineer doesn't write these rules at all. Instead, past data gets fed into a learning algorithm, showing which users watched, liked, or skipped which videos. The algorithm studies this data and finds patterns on its own, connecting what a user does with what they end up watching and enjoying. It can spot patterns a person would never think of, like users who watch mukbang videos at night also enjoy cooking videos. The best part with this is it keeps updating itself as new data comes in, with no one rewriting anything by hand.

## 6. Mini Dataset

| User | Video Watched | Genre | % Completed | Liked? | Recommended Next |
|------|----------------|-------|--------------|--------|--------------------|
| User A | 'Chocolate Palitaw Recipe' | Cooking | 65% | No | 'Merienda Recipes for Lazy People' |
| User A | 'K-pop Music Video' | Music | 88% | Yes | 'CORTIS Performance Video' |
| User B | 'Douyin Makeup Tutorial' | Makeup | 90% | Yes | 'Nina Park Inspired Makeup Look' |
| User B | 'Y2K Outfit Inspo' | Fashion | 100% | Yes | 'Ukay-ukay Haul' |
| User C | 'Valorant Stream' | Games | 40% | No | 'Gaming Meme Compilation' |

## 7. Pattern/Relationship
Looking at the mini data set, a clear pattern shows up. If completion is high and it is also "Liked," this means the user wants more that same genre, and the system will keep giving almost the same content only. User B is finishing 90% Douyin and 100% in Y2K and liked both, so the recommendation given is in the same lane, like a makeup look inspired by a makeup artist and a ukay-ukay haul.

However, if completion is low or there is no like, it will be different. User A is only finishing 65% in the cooking video and also did not like it but is still given another recipe recommendation, just an easier and categorized one this time. This is showing that the system is not dropping the genre right away. Instead, it's trying first a different style in the same genre, like switching from a chocolate dessert to going to simple merienda recipes, before it can be sure that the user is not really interested in cooking. The same thing happens with User C, who only finished 40% of the game stream and did not like it, so the recommendation shifted into something shorter and lighter, like a meme compilation, instead of another long stream.

Basically, what the algorithm is learning is engagement signals like completion rate and likes, together with content attributes like genre and tags, these are the ones telling how confident and cautious the next recommendation will be.

## 8. Explanation of Training Process
To train this system, the algorithm is given a lot of past examples. These are examples of where we already know what video a user was shown and if they actually watched or liked it. During training, the model makes a prediction for each example. Then it compares this to what really happened. It calculates how far off, or the "error," its prediction was. After that, the model slightly adjust its internal settings, or weights, to make that error smaller. This is usually done using a method called gradient descent. This whole process happens again and again, so many times, across the whole dataset. It keeps going until the model prediction starts to match real user behavior consistently. Once the training is done, the model can now generalize. This means it can make fairly accurate predictions even for new users and new videos it has never seen before, just based on the patterns it already learned.

## 9. Short Reflection

**Why is learning data useful instead of manually programming every possible rule?**

Manually programming every rule is just not possible for a problem like video recommendation. This is because the number of possible combinations of users, videos, and preferences is huge and always changing. Learning from data let the system grow automatically. It can give personal recommendations to millions of users without an engineer writing a separate rule for every one of them. It also adjusts on its own as tastes and trends change over time. It can even find small, hidden patterns in behavior that a human would probably never think to write a rule for. This connects to the main problem with traditional programming talked about in the lesson. Rule-based systems are too rigid, and they cannot keep up with tasks, like translation or recommendation, that need too much flexibility for fixed rules to handle well. Machine Learning fixes this by letting the data itself teach the system what the rules should be.
