# API overview

> Movie DataBase API provides a complete and updated data for over 9 milion titles ( movies, series and episodes) Recent titles are updated weekley - Ratings / episodes light are updated daily

# version and state

Version 1 of MoviesDatabase api

# Available Endpoints

Every endpoint returns and object with 'results' key. Endpoints with pages has additional keys -> 'page', 'next', 'entries'

> ALL query parameters are OPTIONAL

## Titles:

Query parameters and model are explain below, in 'Description Of Optionals Query Parameters' and 'Description Of The Information (Models)'

**a. Titles - Multiple:**

- `path:` /titles

- `description:` returns array of titles according to filters / sorting query parameters provided

- `query parameters:` multiple, unique query parameter 'list' that sets the collection you want to query - options available in Utils - Titles Lists
- `model:` title

**b. Titles - By List of Id's:**

- `path:` /x/titles-by-ids

- `description:` returns array of titles according to array of id's provided

- `query parameters:` - info - list ( unique query parameter that sets the collection you want to query) - options available in Utils - Titles Lists - idsList ( the list of id's, must be an array of strings)

- `model:` title

**c. Title:**

- `path:` /titles/{id}
- `path parameter (required) :` id -> imdb id of title
- `description:` returns title acording to filters / sorting query parameters provided
- `query parameters:` info

- `model:` title

**d. Title Rating**

- `path:` /titles/{id}/ratings
- `path parameter (required) :` id -> imdb id of title
- `description:` returns title rating and votes number
- `query parameters:` -
- `model:` rating

**e. Seasons and Episodes**

- `path:` /titles/series/{id}
- `path parameter (required) :` id -> imdb id of series
  description: returns array of episodes only with episode id, episode number and season number in ascending order
- `query parameters:` -

- `model:` light episode

**f. Seasons Number**

- `path:` /titles/seasons/{id}
- `path parameter (required) :` id -> imdb id of series
- `description:` returns number of seasons for the series (integer)

- `query parameters:` -

**g. Episodes Id`s By Series Id and Season**

- `path:` /titles/series/{id}/{season}
- `path parameter (required) :` id -> imdb id of series, season -> season number

- `description:` returns array of episodes only with episode id, season number and episode number (only of the season provided in path)

- `query parameters:` -
- `model:` light episode

**h. Episode**

- `path:` /titles/episode/{id}
- `path parameter (required) :` id -> imdb id of episode
- `description:` returns episode according to filters / sorting query parameters provided
- `query parameters:` info

- `model:` title

**i. Upcoming Titles**

- `path:` /titles/x/upcoming
- `description:` returns array of upcoming titles according to filters / sorting query parameters provided
- `query parameters:` multiple

- `model:` title

# Search

**a. Titles by Keyword**

- `path:` /titles/search/keyword/{keyword}
- `path parameter (required) :` keyword
- `description:` returns array of titles according to filters / sorting query parameters provided and the keyword provided in path
- `query parameters:` multiple

- `model:` title

**b. Titles by Title**

- `path:` /titles/search/title/{title}
- `path parameter (required) :` title -> a title or part of a title

- `description:` returns array of titles according to filters / sorting query parameters provided and the title provided in path
- `query parameters:` multiple, unique query parameter exact that sets the looku to be exact default : false

- `model:` title

**b. Titles by Aka's**

- `path:` /titles/search/akas/{aka}

- `path parameter (required) : `aka -> a aka of a title ( exact only and case sensitive )
- `description:` returns array of titles according to filters / sorting query parameters provided and the aka provided in path, work only for exact matches
- `query parameters:` multiple
- `model:` title

## Actors

**a. Actors**

- `path:` /actors

- `description:` returns array of actors according to filters provided
- `query parameters:` limit, page
- `model:` actor

**b. Actor By Id**

- `path:` /actors/{id}

- `path parameter (required) :` imdb id of actor
- `description:` returns actor details
- `model:` actor

## Utils

**a. Title Type**

- `path:` /title/utils/titleType
- `description:` returs array of title types

**b. Genres**

- `path:` /title/utils/titleType
- `description:` returs array of genres

**c. Titles Lists**

- `path:` /title/utils/lists
- `description:` returns array of lists (for 'list' query parameter)

## Request and Response Format

All request are received as json

## Authentication

> In order to authenticat the alx movie app we are going to implement `if(!res.ok) {...}`to ensure datas are fetched effiecintly from the api also by ensuring correct page is displayed in the right route

## Error Handling

> We're going to implement the try catch method and use a conditional statement to ensure erorrs ar rendered in the right components

## Usage Limits and Best Practices

500,000 entry point resquest per month and 1000 request per hour
