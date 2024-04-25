# Moneyball
## Description
Brief description of what the project does.

## Dependencies
- requests
- json
- pandas

## Usage
1. First, ensure you have all the dependencies installed.
2. Clone this repository.
3. Run the script main.py.
4. Provide necessary input if prompted.
5. View the output or any generated files.

## Querying for Team Names

The provided code snippet queries an API to fetch team names for a specific league and season. Here's a breakdown of what the code does:

- It constructs a URL to make a request to the API endpoint for fetching teams.
- Defines the query parameters, including the league ID and season.
- Sets the necessary headers for accessing the API (you need to fill in the values for "X-RapidAPI-Key" and "X-RapidAPI-Host").
- Makes a GET request to the API endpoint using the `requests.get()` method.
- Prints the JSON response received from the API in a formatted manner using `json.dumps()`.

### Example Output
The JSON response containing information about the teams participating in the specified league and season.

{
    "get": "teams",
    "parameters": {
        "league": "371",
        "season": "2023"
    },
    "errors": [],
    "results": 12,
    "paging": {
        "current": 1,
        "total": 1
    },
    "response": [
        {
            "team": {
                "id": 574,
                "name": "Vardar Skopje",
                "code": "VAR",
                "country": "Macedonia",
                "founded": 1947,
                "national": false,
                "logo": "https://media.api-sports.io/football/teams/574.png"
            },
            "venue": {
                "id": 1045,
...
            }
        }
    ]
}

## Creating a List of League Data

The provided code snippet processes the JSON response obtained from the API to create a list of league data. Here's what the code does:

- Initializes empty lists `team_id` and `team_name` to store information about teams.
- Loops through the JSON response received from the API to extract team IDs and names.
- Appends the extracted team IDs and names to the respective lists.
- Creates a DataFrame `league_df` using the `team_id` and `team_name` lists.
- Prints the first few rows of the DataFrame to display the league data.

### Example Output
The DataFrame `league_df` containing information about teams participating in the specified league and season.

| Team_ID | Team_Name       |
|---------|-----------------|
| 574     | Vardar Skopje   |
| 609     | Shkendija       |
| 663     | FK Rabotnicki   |
| 2265    | Shkupi 1927     |
| 4194    | Akademija Pandev|

## Querying for All Leagues Akademija Pandev (Brera Strumica) Participates In

The provided code snippet queries an API to fetch information about all leagues in which the team "Akademija Pandev (Brera Strumica)" participates. Here's what the code does:

- Constructs a URL to make a request to the API endpoint for fetching leagues.
- Defines the query parameter specifying the team ID.
- Makes a GET request to the API endpoint using the `requests.get()` method.
- Prints the JSON response received from the API in a formatted manner using `json.dumps()`.
- Processes the JSON response to create a DataFrame containing information about the leagues.

### Example Output
The DataFrame `team_league_df` containing information about the leagues in which the team "Akademija Pandev (Brera Strumica)" participates.

| League_ID | League_Name                      | League_Country |
|-----------|----------------------------------|----------------|
| 371       | First League                     | Macedonia      |
| 3         | UEFA Europa League               | World          |
| 667       | Friendlies Clubs                 | World          |
| 756       | Cup                              | Macedonia      |
| 848       | UEFA Europa Conference League    | World          |

## Creating a List of League IDs to Search For

The provided code snippet initializes a list containing the league IDs to be searched for. In this case, it's focusing on the First Macedonia League, identified by the league number '371'. 

## Querying Player Statistics for Specific Leagues and Seasons

The code iterates through specified seasons and pages to retrieve player statistics for the selected league. Here's what the code does:

- Constructs the API endpoint URL for fetching player statistics.
- Defines parameters including the league ID, season, and page number for pagination.
- Iterates through the specified seasons and pages to fetch player data.
- Stores the retrieved player data in a dictionary with keys representing each season and page combination.
- Prints the player data dictionary containing statistics for each season and page in a formatted manner.

### Example Output
The `all_player_info` dictionary containing player statistics for each season and page.
{
    "371_2019": {
        "Page_1": {
            "get": "players",
            "parameters": {
                "league": "371",
                "page": "1",
                "season": "2019"
            },
            "errors": [],
            "results": 20,
            "paging": {
                "current": 1,
                "total": 12
            },
            "response": [
                {
                    "player": {
                        "id": 74642,
                        "name": "Burhan Mustafov",
                        "firstname": "Burhan",
                        "lastname": "Mustafov",
                        "age": 28,
                        "birth": {
                            "date": "1994-03-02",
                            "place": "\n    ",
                            "country": "North Macedonia"
                        },
                        "nationality": "North Macedonia",
                        "height": "\n    ",
                        "weight": "\n    ",
                        "injured": false,
                        "photo": "https://media.api-sports.io/football/players/74642.png"
                    },
                    "statistics": [
                        {
                            "team": {
                                "id": 4331,
                                "name": "Sileks",
                                "logo": "https://media.api-sports.io/football/teams/4331.png"
                            },
                            "league": {
                                "id": 371,
                                "name": "First League",
                                "country": "Macedonia",
                                "logo": "https://media.api-sports.io/football/leagues/371.png",
                                "flag": "https://media.api-sports.io/flags/mk.svg",
                                "season": 2019
                            },
                            "games": {
                                "appearences": 3,
                                "lineups": 3,
                                "minutes": 242,
                                "number": null,
                                "position": "Midfielder",
                                "rating": null,
                                "captain": false
                            },
                            "substitutes": {
                                "in": 0,
                                "out": 2,
                                "bench": 0
                            },
                            "shots": {
                                "total": null,
                                "on": null
                            },
                            "goals": {
                                "total": 1,
                                "conceded": null,
                                "assists": null,
                                "saves": null
                            },
                            "passes": {
                                "total": null,
                                "key": null,
                                "accuracy": null
                            },
                            "tackles": {
                                "total": null,
                                "blocks": null,
                                "interceptions": null
                            },
                            "duels": {
                                "total": null,
                                "won": null
                            },
                            "dribbles": {
                                "attempts": null,
                                "success": null,
                                "past": null
                            },
                            "fouls": {
                                "drawn": null,
                                "committed": null
                            },
                            "cards": {
                                "yellow": 1,
                                "yellowred": 0,
                                "red": 0
                            },
                            "penalty": {
                                "won": null,
                                "commited": null,
                                "scored": null,
                                "missed": null,
                                "saved": null
                            }
                        }
                    ]
                }

## Creating a List of Player Data

The provided code snippet processes the retrieved player information to create a list containing various statistics for each player. Here's what the code does:

- Initializes an empty list `player_table_data` to store player information.
- Loops through the specified league IDs, years, and pages to extract player statistics.
- Extracts various player statistics such as name, age, team, position, appearances, goals, passes, tackles, fouls, cards, penalties, etc.
- Adds the extracted player information to the `player_table_data` list.

### Example Output
The `player_table_data` list containing player statistics for each player in the specified league and season.
| League       | Season | Last Name    | First Name | Age | Country          | Team Name | Position   | Number Of Appearances | Game Time | Number of Sub ins | Number of Sub outs | Number of Times Benched | Total Goals Scored | Total Yellow Cards | Total Red Cards | Total Yellow-Red Cards |
|--------------|--------|--------------|------------|-----|------------------|-----------|------------|-----------------------|------------|-------------------|--------------------|-------------------------|--------------------|---------------------|-----------------|-----------------------|
| First League | 2019   | Mustafov     | Burhan     | 28  | North Macedonia  | Sileks    | Midfielder | 3.0                   | 242.0      | 0.0               | 0.0                | 0.0                     | 1.0                | 1.0                 | 0.0             | 0.0                   |
| First League | 2019   | Drašković    | Srđan      | 30  | Serbia           | Sileks    | Defender   | 20.0                  | 1719.0     | 1.0               | 1.0                | 1.0                     | 6.0                | 0.0                 | 0.0             | 0.0                   |
| First League | 2019   | Blagojević   | Dejan      | 31  | Serbia           | Sileks    | Defender   | 17.0                  | 1530.0     | 0.0               | 0.0                | 0.0                     | 2.0                | 2.0                 | 0.0             | 0.0                   |

# Looping Through DataFrame to Calculate Additional Metrics

The provided code snippet loops through a DataFrame containing player statistics to calculate additional metrics for analysis. Here's what the code does:

- Iterates through each row of the DataFrame.
- Calculates various player performance metrics such as goals per appearance, substitutions per game, average minutes per appearance, yellow card rate, red card rate, and yellow-red card rate.
- Adds the calculated metrics as new columns to the DataFrame.

### Example Output
The DataFrame `player_df` containing the original player statistics along with the newly calculated metrics.
| League       | Season | Last Name   | First Name | Age | Country          | Team Name | Position   | Number Of Appearances | Game Time | Total Yellow Cards | Total Red Cards | Total Yellow-Red Cards | Goals Per Game Time | Goals Per Appearance | Number of Substitutions per Game | Avg Minutes per Appearance | Yellow Card Rate | Red Card Rate | Yellow-Red Card Rate |
|--------------|--------|-------------|------------|-----|------------------|-----------|------------|-----------------------|------------|---------------------|-----------------|------------------------|----------------------|----------------------|--------------------------------|----------------------------|-------------------|---------------|-----------------------|
| First League | 2019   | Mustafov    | Burhan     | 28  | North Macedonia  | Sileks    | Midfielder | 3.0                   | 242.0      | 1.0                 | 0.0             | 0.0                    | 0.004132             | 0.333333             | 0.0                            | 80.666667                  | 0.012397          | 0.0           | 0.0                   |
| First League | 2019   | Drašković   | Srđan      | 30  | Serbia           | Sileks    | Defender   | 20.0                  | 1719.0     | 6.0                 | 0.0             | 0.0                    | 0.000582             | 0.050000             | 0.1                            | 85.950000                  | 0.069808          | 0.0           | 0.0                   |
| First League | 2019   | Blagojević  | Dejan      | 31  | Serbia           | Sileks    | Defender   | 17.0                  | 1530.0     | 2.0                 | 0.0             | 0.0                    | 0.001307             | 0.117647             | 0.0                            | 90.000000                  | 0.022222          | 0.0           | 0.0                   |

## Data Preprocessing and Type Conversion

The provided code snippet performs data preprocessing tasks and converts the data types of columns in the DataFrame `player_df`. Here's what the code does:

- Checks the unique values in the 'Season' column.
- Replaces season numbers with season ranges to make them more descriptive.
- Checks unique team names and replaces them with official listed names for consistency.
- Replaces all missing values (NAs) with 0 for uniformity.
- Defines a dictionary `dtypes_dict` specifying the desired data types for each column.
- Converts the data types of columns in the DataFrame `player_df` according to the specified dictionary.
- Converts the DataFrame `player_df` to a CSV file named 'First_Macedonia_League_Clean.csv'.

### Example Output
The cleaned and preprocessed DataFrame `first_league_df` with updated data types and saved as a CSV file.


                
