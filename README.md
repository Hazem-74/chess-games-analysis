# Chess Games Analysis

This repository, 'Chess Games Analysis' by Hazem-74, contains Jupyter notebooks designed to parse, extract, and analyze historical chess game data from PGN (Portable Game Notation) files. The project provides tools to load game records, extract detailed metadata from game headers, and structure this information for further analytical exploration using Python and popular data science libraries.

## Project Purpose

The primary goal of this project is to facilitate the analysis of chess game history. By processing PGN files, users can gain insights into various aspects of their games or public game databases, such as opening choices, player ratings, game outcomes, and more.

## Files Overview

This repository includes the following Jupyter notebooks:

### `Chess_com.ipynb`

*   **Purpose:** This notebook serves as a foundational script for loading and parsing chess game data directly from a PGN file using the `python-chess` library. It demonstrates the basic steps required to read individual games from a PGN source.
*   **Main Logic:**
    *   Initializes with core libraries `chess.pgn` and `pandas`.
    *   Specifies a PGN file path (e.g., `"lichess_Hazem74.pgn"`).
    *   Reads the PGN file game by game using `chess.pgn.read_game()`.
    *   Stores each parsed `chess.pgn.Game` object in a list.
    *   Provides a count of the total games successfully loaded from the PGN.
*   **Methodology:** Focuses on the iterative parsing of PGN files to access raw `chess.pgn.Game` objects, which contain all game details including headers and move sequences. Although named `Chess_com.ipynb`, the provided code is configured to read from a Lichess PGN, illustrating a general approach applicable to any PGN source.

### `Lichess.ipynb`

*   **Purpose:** Building upon the basic parsing capabilities, this notebook specializes in extracting detailed header information from PGN files and transforming it into a structured Pandas DataFrame. This step is crucial for performing quantitative analysis on game metadata.
*   **Main Logic:**
    *   Imports `chess.pgn` and `pandas` for game parsing and data manipulation.
    *   Specifies a PGN file path (e.g., `"lichess_Hazem74.pgn"`).
    *   Parses games similar to `Chess_com.ipynb`, but additionally extracts `game.headers` for each game.
    *   Identifies and collects all unique PGN header keys (e.g., 'Event', 'Site', 'Date', 'WhiteElo', 'BlackElo', 'Result', 'Opening', 'ECO', etc.) present across all games.
    *   Constructs a Pandas DataFrame where each row represents a game, and columns correspond to the collected PGN header keys, ensuring consistency by filling missing values where a header might not be present for a specific game.
    *   Displays the discovered headers and the head of the resulting DataFrame.
*   **Methodology:** Emphasizes data extraction and transformation. It effectively turns unstructured PGN header data into a clean, tabular format, making it ready for filtering, aggregation, and statistical analysis using Pandas.

## Requirements

To run these notebooks, you will need:

*   Python 3.x
*   Jupyter Notebook (or JupyterLab)
*   The `pandas` library
*   The `python-chess` library

## Installation

You can install the required Python packages using pip:

```bash
pip install jupyter pandas python-chess
```

## Cloning the Repository

To get a local copy of this project, open your terminal or command prompt and run:

```bash
git clone https://github.com/Hazem-74/Chess-Games-Analysis.git
```

## How to Run the Notebooks

1.  **Navigate to the project directory:**
    ```bash
    cd Chess-Games-Analysis
    ```
2.  **Place your PGN file:** Ensure your PGN file (e.g., `lichess_Hazem74.pgn` or any other `.pgn` file you wish to analyze) is located in the root of the `Chess-Games-Analysis` directory, or update the `pgn_file` variable within the notebooks to point to its correct path.
3.  **Start Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```
4.  **Open a notebook:** Your web browser will open, displaying the Jupyter interface. From there, you can open `Chess_com.ipynb` or `Lichess.ipynb`.
5.  **Run cells:** Execute the notebook cells sequentially to see the parsing and data extraction in action.

## Usage Example

After running the `Lichess.ipynb` notebook, you will have a Pandas DataFrame (`df`) containing comprehensive metadata for all your games. This DataFrame can then be used for various analyses, such as:

*   Filtering games by specific players or events.
*   Analyzing win/loss ratios for different openings.
*   Tracking changes in player ratings over time.
*   Identifying common time controls or game variants.

## Contributing

Feel free to fork this repository, submit pull requests, or open issues if you have suggestions, improvements, or encounter any problems.

## License

This project is open-source. Please refer to the repository's license for more details.