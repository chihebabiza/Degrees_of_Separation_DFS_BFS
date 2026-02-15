# Degrees of Separation

A command-line tool that finds the shortest path between any two actors by identifying the movies that connect them. Based on the "Six Degrees of Kevin Bacon" concept, this project utilizes **Breadth-First Search (BFS)** to navigate a database of actors and movies.

## 🚀 Overview

The goal is to find the shortest connection between a **Source** actor and a **Target** actor. Each "degree" represents a movie that two actors starred in together.

For example:

1. **Tom Cruise** and **Jack Nicholson** starred in *A Few Good Men*.
2. **Jack Nicholson** and **Dustin Hoffman** starred in *I'm Still Here*.
3. **Result:** Tom Cruise is 2 degrees away from Dustin Hoffman.

## 🧠 Algorithm

This project implements **Breadth-First Search (BFS)** to guarantee the shortest possible path.

* **Nodes:** Represent people (actors).
* **Actions:** Represent movies that connect people.
* **State:** The unique IMDB ID for each person.
* **Frontier:** A `QueueFrontier` (FIFO) is used to explore neighbors layer by layer.

## 📁 Data

The project can be run with two different datasets provided in the repository:

* `small`: A subset of the IMDB database for quick testing.
* `large`: The full dataset including hundreds of thousands of actors and movies.

Each directory contains:

* `people.csv`: Names and birth years for each actor.
* `movies.csv`: Titles and release years for each movie.
* `stars.csv`: A mapping of which actors starred in which movies.

## 🛠️ Installation & Usage

### 1. Prerequisites

Ensure you have **Python 3.x** installed on your system.

### 2. Run the Program

Navigate to the project directory and run the script:

```bash
# To run with the large dataset (default)
python degrees.py large

# To run with the small dataset
python degrees.py small

```

### 3. Example Input/Output

```text
Loading data...
Data loaded.
Name: Emma Watson
Name: Jennifer Lawrence
3 degrees of separation.
1: Emma Watson and Brendan Gleeson starred in Harry Potter and the Goblet of Fire
2: Brendan Gleeson and Robert De Niro starred in The Good Shepherd
3: Robert De Niro and Jennifer Lawrence starred in Silver Linings Playbook

```

## 🏗️ Project Structure

| File | Description |
| --- | --- |
| `degrees.py` | Main program logic (Loading data and BFS implementation). |
| `util.py` | Classes for `Node`, `StackFrontier` (DFS), and `QueueFrontier` (BFS). |
| `small/` | Directory containing small sample datasets. |
| `large/` | Directory containing full IMDB datasets. |
