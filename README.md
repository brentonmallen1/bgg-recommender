# Boardgamegeek Game Recommender

## Step 1:
A similar game finder.  Given a game title, find games that are similar

Features to use: categories,  description, mechanics, families, max_players, min_players, min_age, max_playing_time, min_playing_time, rating_average_weight

1. Write a script to extract ^ from the top 100 into a dataframe
2. do some NLP on the desctiption
3. Try building a locality sensitive hash
4. build a function that takes a name, calculates the hash and grabs like games (top n games)
  - ensambleLSH I think

goffing around:
```
client = bgg.BGGClient()
a = client.game('Arkham Horror: The Card Game')
b = pd.DataFrame(data={'desc':a.description, 'cat':a.categories, 'mech':a.mechanics
    ...: , 'fam':a.families, 'max_p':a.max_players})
b['desc'] = b.desc.apply(lambda x: str(x).replace("Description from the publisher:"
    ...: , "").replace('\n', ' ').strip())

```
