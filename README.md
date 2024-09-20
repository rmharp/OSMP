# Stable Marriage Problem with Randomized Member Order

## Overview

This repository contains R code that implements the Gale-Shapley algorithm to solve the Stable Marriage Problem, specifically focusing on the Hospital/Resident Assignment Problem. The algorithm assigns 150 fictitious members to 16 projects based on their ranked preferences while respecting the capacity constraints of each project. The implementation includes an option to randomize the order in which members propose to projects, simulating a more equitable assignment process.

## Features

- **Fictitious Data Generation**: Creates random member names and their ranked preferences for projects.
- **Gale-Shapley Algorithm Implementation**: Assigns members to projects based on preferences and capacities.
- **Randomized Member Order**: Option to shuffle the order of member proposals.
- **Outputs**: Saves the final assignments to a CSV file and provides a summary of project assignments.

## Getting Started

### Prerequisites

- **R** (version 3.6.0 or higher)
- **RStudio** (optional but recommended for running RMarkdown files)
- No additional R packages are required (uses base R functions)

### Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/rmharp/SMP.git
   ```
2. **Navigate to the Project Directory**
   
   ```bash
   cd stable-marriage-problem
   ```
3. **Set Up the Data Directory**
   Be sure there's a `data/` directory in the project root to store input and output CSV files.

## Usage

1. **Open the RMarkdown File**

   - Open `Stable_Marriage_Problem.Rmd` in RStudio or your preferred R environment.

2. **Run the Data Generation Code**

   - Execute the first code chunk to generate fictitious members and their project preferences.
   - This will create `member_preferences.csv` in the `data/` directory.

3. **Configure Algorithm Settings**

   - In the second code chunk, you can set the `deterministic` variable:
     - `deterministic <- FALSE` (default): Members propose in a random order.
     - `deterministic <- TRUE`: Members propose in a fixed order.

4. **Run the Gale-Shapley Algorithm**

   - Execute the second code chunk to run the assignment algorithm.
   - This will output `assignments_output.csv` in the `data/` directory and display a summary.

5. **View the Results**

   - Check the console for the project assignment summary.
   - Open `assignments_output.csv` to see individual member assignments.

## Project Structure

- `Stable_Marriage_Problem.Rmd`: Main RMarkdown file containing the code.
- `data/`: Directory containing input and output CSV files.
  - `member_preferences.csv`: Generated member preferences.
  - `assignments_output.csv`: Resulting assignments after running the algorithm.

## Code Explanation

### Data Generation

- **Member Names**: Generates 150 random member names by combining first and last names from predefined lists.
- **Preferences**: Assigns each member a random ranking of 16 projects.
- **Output**: Saves the generated data to `data/member_preferences.csv`.

### Gale-Shapley Algorithm Implementation

- **Reading Preferences**: Reads member preferences from `data/member_preferences.csv`.
- **Project Capacities**: Defines capacities for each project in the `project_capacities` vector.
- **Assignment Process**:
  - Initializes a list of free members.
  - Optionally shuffles the free members list if `deterministic <- FALSE`.
  - Members propose to projects based on their preferences.
  - Projects accept members until capacity is reached.
  - Unassigned members continue to propose to their next preferred project.
- **Outputs**:
  - Assignment summary printed in the console.
  - Final assignments saved to `data/assignments_output.csv`.

## Theoretical Background

### Stable Marriage Problem

The Stable Marriage Problem involves matching members of two sets (e.g., men and women, residents and hospitals) based on their preferences such that no pair would prefer each other over their current matches. A matching is stable if there are no two participants who would both rather be matched with each other than their current partners.

### Gale-Shapley Algorithm

Developed by David Gale and Lloyd Shapley, this algorithm finds a stable matching by having one set of participants (proposers) propose to the other set (receivers) in order of preference.

- **Hospital/Resident Assignment Problem**: An extension where one side (hospitals/projects) can accept multiple matches up to a capacity limit.

### Randomized Member Order

Randomizing the order in which members propose can simulate fairness and reduce bias that might result from processing members in a fixed order.

## Customization

- **Adjust Number of Members or Projects**: Modify `n_members` and `n_projects` variables in the first code chunk.
- **Change Project Capacities**: Update the `project_capacities` vector in the second code chunk.
- **Set Deterministic or Random Order**: Change the `deterministic` variable to `TRUE` or `FALSE`.

## Sample Output

```yaml
Project Assignment Summary:
Project 1 :  5 / 5 members assigned
Project 2 :  3 / 3 members assigned
Project 3 :  4 / 4 members assigned
Project 4 :  5 / 5 members assigned
Project 5 :  3 / 3 members assigned
Project 6 :  5 / 5 members assigned
Project 7 :  3 / 3 members assigned
Project 8 :  4 / 4 members assigned
Project 9 :  5 / 5 members assigned
Project 10 :  5 / 5 members assigned
Project 11 :  5 / 5 members assigned
Project 12 :  5 / 5 members assigned
Project 13 :  4 / 4 members assigned
Project 14 :  5 / 5 members assigned
Project 15 :  3 / 3 members assigned
Project 16 :  3 / 3 members assigned

Number of unassigned members: 76
```

## Contributing

Contributions are welcome! To contribute:

1. **Fork the Repository**

   Click the "Fork" button at the top right of the repository page.

2. **Create a Branch**

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Commit Your Changes**

  ```bash
  git commit -am 'Add your feature'
  ```

4. **Push to the Branch**

   ```bash
   git push origin feature/your-feature-name
   ```

5. **Open a Pull Request**

   Submit your pull request for review.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

- **Author**: *Riley Harper
- **Email**: *riley.harper@unc.edu*
- **GitHub**: [rmharp](https://github.com/rmharp)

## Acknowledgments

- **David Gale and Lloyd Shapley** for developing the Gale-Shapley algorithm.
- **National Resident Matching Program (NRMP)** for inspiration on the matching process.

## Further Reading

- **Stable Marriage Problem**: [Wikipedia](https://en.wikipedia.org/wiki/Stable_marriage_problem)
- **Gale-Shapley Algorithm**: [Original Paper](https://www.jstor.org/stable/2312726)
- **Hospital/Resident Problem**: [Wikipedia](https://en.wikipedia.org/wiki/Stable_marriage_problem#Hospital/resident_problem)

---

Feel free to explore, modify, and enhance the code to suit your needs. If you have any questions or run into issues, please open an issue or contact me directly.
