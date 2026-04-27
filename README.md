# Degrees of Separation

This Python program implements the "Six Degrees of Kevin Bacon" game, finding the shortest path between two actors through movies they've starred in together.

## Overview

The program uses breadth-first search (BFS) to find the minimum number of connections between any two actors in a movie database. It loads data from CSV files containing information about people, movies, and movie casts.

## Files

- `degrees.py`: Main program that loads data and finds degrees of separation
- `util.py`: Contains data structures for BFS (Node, StackFrontier, QueueFrontier)
- `Programmier_Assignment_1.pdf`: Assignment description (in German)

## Data Format

The program expects three CSV files in a data directory:

- `people.csv`: Contains actor information (id, name, birth year)
- `movies.csv`: Contains movie information (id, title, year)
- `stars.csv`: Links actors to movies (person_id, movie_id)

## Usage

1. Place the CSV data files in a directory (e.g., `large/` or `small/`)
2. Run the program:

```bash
python degrees.py [directory]
```

If no directory is specified, it defaults to `large`.

3. Enter the names of two actors when prompted
4. The program will display the degrees of separation and the connection path

## Example

```
Loading data...
Data loaded.
Name: Kevin Bacon
Name: Tom Hanks
2 degrees of separation.
1: Kevin Bacon and Kyra Sedgwick starred in Pyrates
2: Kyra Sedgwick and Tom Hanks starred in Something's Gotta Give
```

## Implementation

The `shortest_path` function in `degrees.py` implements BFS using a queue frontier to find the shortest path between actors. Each "step" in the path represents co-starring in a movie.

## Requirements

- Python 3.x
- CSV data files in the expected format

## Group Submission Details

- **Course:** KI mit Python (SS 2026)
- **Deadline:** April 30, 2026, 12:00 PM
- **Team Members:** Samuel Atama, Malik Yildizhan, Santiago Meijide, Julian Soady, Elyas Mouhkli
- **Target Group:** WWIMBIT23A

## Notes

This is an implementation of the classic "Six Degrees of Kevin Bacon" concept, where most actors can be connected through a surprisingly small number of movie co-stars.
