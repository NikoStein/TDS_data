# F1 Fake API Documentation

This API provides data related to Formula 1 races, constructors, and seasons.

## Endpoints

### `/f1fakeapi/constructors.json`

- **Method:** GET
- **Description:** Get a list of all constructors.
- **Response:** A JSON object containing a list of all constructors. Each constructor has properties such as `constructorId`, `name`, `nationality`, `url`.

### `/f1fakeapi/constructors/{constructorId}`

- **Method:** GET
- **Description:** Get details of a specific constructor by its `constructorId`.
- **Response:** A JSON object containing details of the specified constructor, including the results of all the races won by the constructor.

### `/f1fakeapi/constructors/{constructorId}/results/1.json`

- **Method:** GET
- **Description:** Get the results of all races by a specific constructor.
- **Response:** A JSON object containing details of all races won by the specified constructor.

### `/f1fakeapi/{year}.json`

- **Method:** GET
- **Description:** Get a list of all races in a specific year.
- **Response:** A JSON object containing a list of all races in the specified year. Each race has properties such as `raceId`, `year`, `round`, `circuitId`, `raceName`, `date`, `time`, `url`.

### `/f1fakeapi/{year}/{round}`

- **Method:** GET
- **Description:** Get the details of a specific round in a specific year.
- **Response:** A JSON object containing details of the specified round.

### `/f1fakeapi/{year}/{round}/results.json`

- **Method:** GET
- **Description:** Get the results of a specific round in a specific year.
- **Response:** A JSON object containing the results of the specified round. The results include the `constructorId` and `name` (name of the constructor).

### `/f1fakeapi/seasons.json`

- **Method:** GET
- **Description:** Get a list of all seasons.
- **Response:** A JSON object containing a list of all seasons. Each season has properties such as `year`, `url`.

## Note on naming conventions

- In the JSON files, the term "constructor" refers to the team that constructed the car.
- In the R code consuming this API, the "name" field from the JSON is referred to as "raceName" to avoid ambiguity with other fields named "name" (like constructor name).
- Similarly, for constructor results the `constructorId` and `name` (name of the constructor) are merged into a single 'Constructor' field containing both values for each result.
