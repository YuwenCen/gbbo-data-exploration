# gbbo-data-exploration

# Great British Bake Off — An Informal Data Exploration

This is an **informal data project** on *The Great British Bake Off* 
Instead of a “paper-style” report, this repo is built around a Jupyter notebook that mixes story + visuals + lightweight statistical reasoning.

I explore questions that Bake Off fans often argue about, like:
- “Are technical challenges getting harder over time?”
- “Does the show favor younger bakers?”
- “Do Hollywood Handshakes actually mean someone is more skilled?”
- “Which judges are the most ‘evil’ in technical challenges?”
- “What ingredients show up most in signature bake titles?”

---

## What’s Inside
This project lives mainly in one notebook and is split into themed sections:

### 1) Exploratory Data Analysis
- Quick summaries and visualizations to understand:
  - technical recipe complexity over seasons
  - baker demographics (age, occupation, gender distribution)

### 2) “Popular Ingredients” from Recipe Titles
We don’t have full ingredient lists, but we *do* have recipe titles for Signature and Showstopper bakes.
So I:
- cleaned and tokenized signature titles
- removed filler words and “week theme” words (e.g., “bread”, “cake”)
- counted the most common remaining words as a proxy for popular flavors/ingredients
- compared words used by bakers who were **eliminated** vs those who **stayed**

### 3) Gender Balance: Is the Cast 50/50?
I checked whether the show’s baker selection *looks* different from a 50/50 gender split.
- Built a simple simulation test under a 50/50 null model
- Compared the observed female proportion to simulated outcomes

### 4) Technical Skill: Winners vs Non-winners (Permutation Test)
Technical ranks are tricky because the number of contestants changes each week.
So I converted each technical rank into a **percentile**, controlling for how many contestants were still in the competition.

Then I ran permutation tests for:
- **Winners vs non-winners**
- **Handshake recipients vs non-handshake recipients**

### 5) Are Certain Judges More “Devilish”?
Fans claim Paul’s technicals are brutal. The data suggests something even spicier:
- using recipe complexity features (DifficultyScore, ingredients, components, dishes, instruction length)
- estimated each judge’s average difficulty using **bootstrapping**
- compared distributions and confidence intervals

### 6) Probability Playground
A small section practicing conditional probability using Bake Off outcomes:
- e.g., probability a season winner was a Star Baker at least once
- probability a randomly selected contestant set includes a winner

### 7) Recipe Name Generator (for fun)
A probabilistic recipe-title generator using:
- word categories (ingredients / items / extras)
- multiple templates
- probability distributions for certain word choices

### 8) Dishwashing: Does Difficulty Mean More Dishes?
A simple regression / correlation exploration:
- scatter plots and fitted line
- correlation in standard units
- predicted values overlay

---

## Data
The notebook uses multiple public datasets (CSV files) compiled from different sources, so season coverage may vary:

- `baker_weeks.csv` — baker-level weekly outcomes (baker × episode)
- `challenge_results.csv` — recipe titles and challenge outcomes
- `technical_challenge_recipes.csv` — technical recipes + difficulty/complexity metrics
- `bakers.csv` — baker demographics + summary technical stats

