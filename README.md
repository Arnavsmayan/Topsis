# TOPSIS Algorithm - Ranking Made Simple

Welcome to this Python implementation of **TOPSIS** (Technique for Order Preference by Similarity to Ideal Solution), a method used to rank alternatives based on a set of decision-making criteria. This project aims to simplify complex decision-making processes by using mathematical formulas to calculate the best options.

## How Does It Work?

Imagine you’re comparing different models of smartphones based on various features like price, storage, camera quality, and design. Instead of relying on your gut feeling, TOPSIS normalizes the data, assigns weights to each feature (e.g., you care more about camera quality than looks), and then calculates the distance between each model and an ideal solution. The closer a model is to the "best-case scenario," the better its rank.

## What You'll Need

To get started, you'll need:
- Python 3.7 (preferably)
- **Pandas** for data handling
- **NumPy** for numerical calculations

To install the dependencies, just run:

```bash
pip install pandas numpy
```

## How to Run the Script

### Command-Line Execution

Here’s the command you’ll use to run the script:

```bash
python 102203979_main.py <inputFileName> <Weights> <Impacts> <resultFileName>
```

Where:
- `<inputFileName>` is your CSV file that holds the data. It should have one column for alternatives and the rest for decision-making criteria (e.g., price, storage, camera).
- `<Weights>` is a comma-separated string that specifies the importance (weight) of each criterion.
- `<Impacts>` is another comma-separated string, indicating whether a criterion is beneficial (`+`) or non-beneficial (`-`).
- `<resultFileName>` is where you want to save the output, containing the scores and ranks.

### Example

Let’s say we have a CSV file named `input_data.csv` and we want to weigh the features as 20%, 30%, 30%, and 20%, respectively, with the first three being beneficial and the last one (Looks) being non-beneficial.

Run:

```bash
python topsis.py input_data.csv 0.2,0.3,0.3,0.2 +,+,+,- result.csv
```

This command will process the data, calculate the scores, and save the results in a file called `result.csv`.

## Input File Structure

The CSV file should look something like this:

```csv
Model,Price,Storage,Camera,Looks
M1,250,16,12,5
M2,200,16,8,3
M3,300,32,16,4
M4,275,32,8,4
M5,225,16,16,2
```

Here, each row represents a different alternative (e.g., smartphone model) and each column represents a decision-making criterion.

## Output Format

After running the script, the output will look like this:

```csv
Model,Price,Storage,Camera,Looks,Score,Rank
M1,250,16,12,5,0.4459,5
M2,200,16,8,3,0.3700,6
M3,300,32,16,4,0.6299,2
M4,275,32,8,4,0.4936,3
M5,225,16,16,2,0.4758,4
```

The **Score** is a measure of how close each alternative is to the ideal solution, and the **Rank** shows the order of preference, with 1 being the best choice.

## Handling Errors

The script takes care of common mistakes:
- If your input file doesn’t exist, it’ll raise a `FileNotFoundError`.
- If you mismatch the number of weights and impacts, or if you provide incorrect impacts (e.g., using anything other than `+` or `-`), you’ll get a `ValueError`.

## License

This project is licensed under the MIT License. Feel free to use, modify, or contribute!
