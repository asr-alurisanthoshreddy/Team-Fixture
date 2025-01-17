In this project, I developed an algorithm to generate football match fixtures for the **XYZ Premier League**, which involves 10 teams. The league rules specify that each team must play every other team twice, once at their home stadium and once away. To ensure fairness, teams from the same local town should only face each other after they have played against teams from other towns. Additionally, the fixtures are designed such that only 4 teams play each weekend, with each weekend featuring two matches. The program outputs the generated fixtures in a CSV file and displays them on-screen for easy reference.

The solution begins by reading the team data from a CSV file and creating objects to represent each team. Each team is paired with every other team to create a list of matches. The program then applies the **Fisher-Yates shuffle** algorithm to randomize the order of the matches, ensuring fairness in match scheduling. Afterward, the matches are sorted by leg (first leg before the second leg), and then grouped into weekends, with each weekend containing two matches. The program also ensures that local teams face each other only after playing teams from other towns. Finally, the program writes the generated weekend fixtures to an output CSV file and displays them on the screen.

### Example of Team List (with new names):

| Team Name           | Local Town | Team Stadium  |
| ------------------ |:----------:|:-------------:|
| Thunder FC          | Springfield | Thunder Arena |
| River City United   | Springfield | River Arena   |
| Mountain FC         | Boulder    | Mountain Grounds |
| Seaside Warriors    | Boulder    | Seaside Park  |
| Desert Lions        | Tucson     | Desert Field  |
| Canyon Eagles       | Tucson     | Canyon Arena  |
| Greenfield Rangers  | Greenfield | Greenfield Stadium |
| Skyline FC          | Greenfield | Skyline Park  |
| Bay Area FC         | Bayview    | Bayview Field |
| Sunset FC           | Bayview    | Sunset Grounds |

The `Team` structure consists of the team’s name, local town, and stadium. The `Match` structure pairs two teams together, and it also tracks whether the match is a local derby and the leg number (first or second). The `Weekend` structure groups two matches that will be played in the same weekend. The utility class provides various methods, such as reading team data from a CSV file, generating matches, creating weekend games, and outputting the fixtures in a structured format. Additionally, it includes methods to display the teams, matches, and fixtures on-screen.

In terms of performance, the time complexity for generating matches (`createMatches()`) is `O(n^2)` due to the nested loops required for pairing teams. The time complexity for grouping matches into weekends (`createWeekendGames()`) is `O(n)`, as it involves a single loop to organize matches. The Fisher-Yates shuffle algorithm (`shuffleMatches()`) has a time complexity of `O(n)` since it iterates through the matches once to randomize them. Sorting the matches by leg (`sortMatches()`) is done using bubble sort with a time complexity of `O(n^2)`.

This approach provides an efficient way to generate a football league’s fixtures while adhering to the specified constraints and ensuring a fair distribution of matches.
