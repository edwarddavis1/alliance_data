# Country Alliance Dataset

Provides a (non-exhaustive) list of military alliances over time. 

## Data structure
- Each line represents either a completely new alliance, or that certain countries have joined/left the alliance.
- **Year**: There is a year for the start of the alliance and (if the alliance has since ended) and a year for the end of the alliance. 
- **Alliance name**: The name of the alliance.
- **Members**: after the alliance name, there is a TAB-separated list of countries that are a part of that alliance.

## Example
If alliance_1 starts in 2018 between country_1 and country_2 and then country_3 joins in 2020, the following is how the data would be represented if the alliance has not changed since 2020.

```
  2018-2020 alliance_1  country_1 country_2
  2020  alliance_1  country_1 country_2 country_3
```

## Reading in data with pandas
```
df = pd.read_csv("timestamped_alliances_sept2022_processed.txt",
                 delimiter="\t", header=None)
df.columns = ["Year", "Alliance", "Members"]
```

## Source
Data taken from wikipedia page of military alliances: https://en.m.wikipedia.org/wiki/List_of_military_alliances (accessed September 2022).
