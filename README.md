# Chess Games History Analysis

## Project Overview

This Python-based analysis tool processes and analyzes chess game history from PGN (Portable Game Notation) files. The script provides comprehensive insights into chess performance, including rating progression, opening statistics, win/loss patterns, and machine learning-based outcome prediction.

## Features

### Game Statistics
- Overall win/loss/draw percentages
- Performance analysis by color (White/Black)
- Time control category breakdown (Bullet, Blitz, Rapid, Classical)
- Rating progression tracking

### Opening Analysis
- Win rates for specific openings
- Performance by opening family and ECO codes
- Color-specific opening success rates
- Top and bottom performing openings

### Performance Metrics
- Rating difference analysis
- Game termination patterns
- ECO category distribution
- Historical rating trends

### Machine Learning
- Game outcome prediction using Random Forest and Gradient Boosting classifiers
- Feature importance analysis
- Win probability estimation
- Model performance comparison

## Installation Requirements

### Prerequisites
- Python 3.7+
- Jupyter Notebook (optional)

### Required Libraries
```
pip install chess pandas matplotlib seaborn numpy scikit-learn
```

### Core Dependencies
- chess: PGN file parsing
- pandas: Data manipulation and analysis
- matplotlib & seaborn: Data visualization
- numpy: Numerical operations
- scikit-learn: Machine learning models

## Usage Instructions

1. Place your PGN file in the project directory
2. Update the username in the script (line 76) to match your chess username
3. Run the Jupyter notebook or Python script

### Configuration
```python
# Set your PGN file path
pgn_file = "your_games.pgn"

# Set your username
your_username = 'YourUsername'
```

## Output and Analysis

### Visualizations
- Rating progression over time
- Opening performance charts
- ECO code distribution
- Win rate vs rating difference
- Model performance comparisons

### Statistical Reports
- Overall performance summary
- Color-based performance analysis
- Time control statistics
- Opening success rates
- Machine learning model accuracy

### Machine Learning Features
The ML models use the following features for prediction:
- Your rating
- Opponent rating
- Rating difference
- Color (White/Black)
- ECO code
- Time control category
- Opening name

## Key Functions

### Data Processing
- PGN file parsing and cleaning
- Feature engineering (rating difference, time categories)
- Opening family extraction
- Result classification

### Analysis Functions
- `categorize_time_control()`: Classifies time controls
- `determine_result()`: Determines game outcome
- `predict_game_outcome()`: Predicts win probability for future games

### Machine Learning
- Random Forest Classifier
- Gradient Boosting Classifier
- Model evaluation and comparison
- Feature importance analysis


## Customization

### For Different Users
1. Change the `your_username` variable to match your chess username
2. Update the PGN file path to point to your game history
3. Adjust visualization parameters as needed

### For Different Time Controls
Modify the `categorize_time_control()` function to adjust time control thresholds:
- Bullet: < 3 minutes
- Blitz: 3-8 minutes
- Rapid: 8-25 minutes
- Classical: > 25 minutes
  
## Limitations

1. Requires standard PGN format from Lichess or Chess.com
2. Assumes consistent username across all games
3. Machine learning accuracy depends on dataset size
4. Time control categorization based on base time only

## Future Enhancements

1. Add move-by-move analysis
2. Incorporate engine evaluation data
3. Support for multiple PGN files
4. Advanced opening repertoire analysis
5. Interactive web interface

## License

This project is open source and available for educational and personal use.

## Acknowledgments

- Uses the `python-chess` library for PGN parsing
- Built with scikit-learn for machine learning components
- Designed for compatibility with Lichess and Chess.com PGN exports
