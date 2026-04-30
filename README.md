# Degrees of Separation

This Python program implements the "Six Degrees of Kevin Bacon" game, finding the shortest path between two actors through movies they've starred in together.

## Group Submission Details

- **Course:** KI mit Python (Sommersemester 2026)
- **Deadline:** April 30, 2026, 12:00 PM
- **Team Members:** Samuel Atama, Malik Yildizhan, Santiago Meijide, Julian Soady, Elyas Mouhkli
- **Target Group:** WIMBIT23A

## Overview

The program uses breadth-first search (BFS) to find the minimum number of connections between any two actors in a movie database. It loads data from CSV files containing information about people, movies, and movie casts.

## Project Structure

```
.
├── README.md
├── large/                 # Large dataset directory
│   ├── people.csv
│   ├── movies.csv
│   └── stars.csv
├── small/                 # Small dataset directory (for testing)
│   ├── people.csv
│   ├── movies.csv
│   └── stars.csv
├── python/                # Source code directory
│   ├── degrees.py         # Main program
│   └── util.py            # BFS data structures
└── pdf/
    └── Programmier_Assignment_1.pdf  # Assignment description (in German)
```

## Files

- `python/degrees.py`: Main program that loads data and finds degrees of separation
- `python/util.py`: Contains data structures for BFS (Node, StackFrontier, QueueFrontier)
- `pdf/Programmier_Assignment_1.pdf`: Assignment description (in German)

## Data Format

The program expects three CSV files in a data directory:

- `people.csv`: Contains actor information (id, name, birth year)
- `movies.csv`: Contains movie information (id, title, year)
- `stars.csv`: Links actors to movies (person_id, movie_id)

## Usage

1. Run the program from the project root directory:

```bash
python3 python/degrees.py [directory]
```

If no directory is specified, it defaults to `large`.

2. Enter the names of two actors when prompted
3. The program will display the degrees of separation and the connection path

## Example Output

```
Loading data...
Data loaded.
Name: Emma Watson
Name: Jennifer Lawrence
3 degrees of separation.
1: Emma Watson and Daniel Radcliffe starred in Harry Potter and the Prisoner of Azkaban
2: Daniel Radcliffe and Woody Harrelson starred in Lost in London
3: Woody Harrelson and Jennifer Lawrence starred in The Hunger Games: Mockingjay - Part 2
```

## Testing

The project includes both small and large datasets:

- **Small dataset**: Contains 16 actors and 5 movies for quick testing
- **Large dataset**: Contains 1,044,499 actors and 344,276 movies with much larger connections

To test with the small dataset:

```bash
python3 python/degrees.py small
```

## Implementation

The `shortest_path` function in `degrees.py` implements BFS using a queue frontier to find the shortest path between actors. Each "step" in the path represents co-starring in a movie.

## Requirements

- Python 3.x
- CSV data files in the expected format

## Notes

This is an implementation of the classic "Six Degrees of Kevin Bacon" concept, where most actors can be connected through a surprisingly small number of movie co-stars.
