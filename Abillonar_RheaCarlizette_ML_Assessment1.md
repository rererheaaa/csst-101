# CSST101 - BASIC MACHINE LEARNING

**NAME:** RHEA CARLIZETTE T. ABILLONAR
**SUBMITTED TO:** SIR MARK BERNARDINO
**SECTION:** BSCS - 3B

---

# Performance Task 1: From Data to Prediction – Analyzing Real-World Machine Learning Applications

## Title
The Algorithm Behind Your Scroll: Machine Learning in Content and Video Recommendation Systems

## Part A – Identify the ML Problem

| Question | Your Answer |
|---|---|
| 1. What is the application? | Content/Video Recommendation, the systems used by streaming platforms like YouTube, TikTok, Netflix, and Instagram to suggest what a user should watch next. |
| 2. What problem are you trying to solve? | Given one user and a huge library of videos, the system needs to predict which few videos that user is most likely to watch, enjoy, and stay engaged with. There is no single rule that works for everyone, since different users like different things, and even the same user's taste changes depending on the moment. |
| 3. What are the inputs? | Watch history, engagement signals such as percent completed, likes, shares, comments, and skips, search queries and browsing behavior, video metadata like genre, tags, length, and creator, and contextual data like time of day and device type. |
| 4. What is the expected output? | A ranked list of videos the user is likely to watch next, or a predicted confidence score showing how likely the user is to engage with each candidate video. |
| 5. What patterns or relationships might the ML system learn? | Users who watch and finish videos in a certain genre while liking them tend to want more of that same genre. Users with low completion and no like signal the system to shift away from that genre instead of recommending more of it. |
| 6. What data would the system need? | Historical records of user-video interactions, meaning which videos were watched, how much of each was completed, whether it was liked, and metadata about each video. |

## Part B – Traditional Programming vs. Machine Learning

**Traditional Programming**

In a traditional programming approach, an engineer writes exact rules by hand, like "if a user watched a K-pop video, recommend other K-pop videos." This does not work well. It cannot handle millions of users and videos. It cannot notice small differences in taste, like a user who likes girl groups but not boy groups. And every time viewing trends change, someone has to go back and rewrite the rules.

**Machine Learning**

In the Machine Learning approach, the engineer does not write these rules at all. Instead, past data gets fed into a learning algorithm, showing which users watched, liked, or skipped which videos. The algorithm studies this data and finds patterns on its own, connecting what a user does with what they end up watching and enjoying. It can spot patterns a person would never think of, like users who watch mukbang videos at night also enjoy cooking videos. Best part is, it keeps updating itself as new data comes in, with no one rewriting anything by hand.

## Part C – Create Your Own Mini Dataset

Below is a simple dataset showing the relationship between how many same-genre videos a user watches with high completion and a like, and the predicted confidence score for recommending another video from that genre.

| Input (same-genre videos watched, high completion + liked) | Output (predicted recommendation confidence score) |
|---|---|
| 1 | 20 |
| 2 | 40 |
| 3 | 60 |
| 4 | 80 |
| 5 | ? |

1. **Pattern:** Every additional same-genre video watched with high completion and a like raises the confidence score by 20 points.
2. **Missing output:** For 5 videos watched, the confidence score would be 100.
3. **Mathematical relationship/function:** y = 20x, where x is the number of same-genre videos watched with high completion and a like, and y is the predicted confidence score.
4. **How a Machine Learning algorithm could learn this relationship:** If the algorithm is given many examples like this, pairing the number of engaged same-genre videos with the actual confidence or engagement score, it would adjust its internal weights little by little until its predictions match the real pattern in the data. Over time, it would end up learning something close to this 20x relationship on its own, without anyone directly telling it the formula.

## Part D – Explain the Training Process

**How does a Machine Learning algorithm learn from data?**

The algorithm starts with input data, like a user's watch history and engagement signals, along with the known output, like whether the user actually watched or liked a video. During training, it makes a prediction and compares it to the real output, then adjusts its internal settings to make its guesses closer to what really happened. It repeats this process many times across the whole dataset, slowly learning the relationship between input and output. Once it has learned this relationship well enough, it can use it to make a prediction for a new user or a new video it has never seen before.

## Short Reflection

**Why is learning data useful instead of manually programming every possible rule?**

Manually programming every rule is just not possible for a problem like video recommendation. This is because the number of possible combinations of users, videos, and preferences is huge and always changing. Learning from data let the system grow automatically. It can give personal recommendations to millions of users without an engineer writing a separate rule for every one of them. It also adjusts on its own as tastes and trends change over time. It can even find small, hidden patterns in behavior that a human would probably never think to write a rule for. This connects to the main problem with traditional programming talked about in the lesson. Rule-based systems are too rigid, and they cannot keep up with tasks, like translation or recommendation, that need too much flexibility for fixed rules to handle well. Machine Learning fixes this by letting the data itself teach the system what the rules should be.
