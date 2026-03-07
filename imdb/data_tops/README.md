[![Discord](https://img.shields.io/discord/1379929746875617413?logo=discord&logoColor=white)](https://discord.gg/4uE6uFGyP7)

# IMDb Dataset Tops

This directory contains 100 rows of each table in the [IMDb non-commercial datasets](https://developer.imdb.com/non-commercial-datasets/) to give users a sense of the schema and data in the dataset, so they can _chat with the data more effectively_ in the [Snow Leopard Discord Chatbot](https://discord.gg/4uE6uFGyP7).

More information about the dataset can be found in the [main IMDb README](https://github.com/SnowLeopard-AI/discord_datasets/tree/main/imdb).

## IMDb Dataset Schemas

### [title.akas](https://github.com/SnowLeopard-AI/discord_datasets/blob/main/imdb/data_tops/title.akas.tsv)
| Field | Type | Description |
|-------|------|-------------|
| titleId | string | A tconst, an alphanumeric unique identifier of the title |
| ordering | integer | A number to uniquely identify rows for a given titleId |
| title | string | The localized title |
| region | string | The region for this version of the title |
| language | string | The language of the title |
| types | array | Enumerated set of attributes for this alternative title. One or more of the following: "alternative", "dvd", "festival", "tv", "video", "working", "original", "imdbDisplay". New values may be added in the future without warning |
| attributes | array | Additional terms to describe this alternative title, not enumerated |
| isOriginalTitle | boolean | 0: not original title; 1: original title |

### [title.basics](https://github.com/SnowLeopard-AI/discord_datasets/blob/main/imdb/data_tops/title.basics.tsv)
| Field | Type | Description |
|-------|------|-------------|
| tconst | string | Alphanumeric unique identifier of the title |
| titleType | string | The type/format of the title (e.g. movie, short, tvseries, tvepisode, video, etc) |
| primaryTitle | string | The more popular title / the title used by the filmmakers on promotional materials at the point of release |
| originalTitle | string | Original title, in the original language |
| isAdult | boolean | 0: non-adult title; 1: adult title |
| startYear | YYYY | Represents the release year of a title. In the case of TV Series, it is the series start year |
| endYear | YYYY | TV Series end year. '\N' for all other title types |
| runtimeMinutes | integer | Primary runtime of the title, in minutes |
| genres | string array | Includes up to three genres associated with the title |

### [title.crew](https://github.com/SnowLeopard-AI/discord_datasets/blob/main/imdb/data_tops/title.crew.tsv)
| Field | Type | Description |
|-------|------|-------------|
| tconst | string | Alphanumeric unique identifier of the title |
| directors | array of nconsts | Director(s) of the given title |
| writers | array of nconsts | Writer(s) of the given title |

### [title.episode](https://github.com/SnowLeopard-AI/discord_datasets/blob/main/imdb/data_tops/title.episode.tsv)
| Field | Type | Description |
|-------|------|-------------|
| tconst | string | Alphanumeric identifier of episode |
| parentTconst | string | Alphanumeric identifier of the parent TV Series |
| seasonNumber | integer | Season number the episode belongs to |
| episodeNumber | integer | Episode number of the tconst in the TV series |

### [title.principals](https://github.com/SnowLeopard-AI/discord_datasets/blob/main/imdb/data_tops/title.principals.tsv)
| Field | Type | Description |
|-------|------|-------------|
| tconst | string | Alphanumeric unique identifier of the title |
| ordering | integer | A number to uniquely identify rows for a given titleId |
| nconst | string | Alphanumeric unique identifier of the name/person |
| category | string | The category of job that person was in |
| job | string | The specific job title if applicable, else '\N' |
| characters | string | The name of the character played if applicable, else '\N' |

### [title.ratings](https://github.com/SnowLeopard-AI/discord_datasets/blob/main/imdb/data_tops/title.ratings.tsv)
| Field | Type | Description |
|-------|------|-------------|
| tconst | string | Alphanumeric unique identifier of the title |
| averageRating | decimal | Weighted average of all the individual user ratings |
| numVotes | integer | Number of votes the title has received |

### [name.basics](https://github.com/SnowLeopard-AI/discord_datasets/blob/main/imdb/data_tops/name.basics.tsv)
| Field | Type | Description |
|-------|------|-------------|
| nconst | string | Alphanumeric unique identifier of the name/person |
| primaryName | string | Name by which the person is most often credited |
| birthYear | YYYY | Birth year in YYYY format |
| deathYear | YYYY | Death year in YYYY format if applicable, else '\N' |
| primaryProfession | array of strings | The top-3 professions of the person |
| knownForTitles | array of tconsts | Titles the person is known for
