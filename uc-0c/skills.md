# skills.md
# INSTRUCTIONS: Generate a draft by prompting AI, then manually refine this file.
# Delete these comments before committing.

skills:
  - name: load_dataset
    description: Reads the budget CSV, validates required columns, and reports missing values before returning data.
    input: Filepath to the dataset CSV (String).
    output: Parsed data structure along with a log of total null entries and their specific rows (Object/Tuple).
    error_handling: Halts execution and notifies if required columns are missing or file is fundamentally corrupt.

  - name: compute_growth
    description: Computes growth metrics across specific ward and category combinations while preserving logic transparency.
    input: Filter parameters (ward, category), growth_type (e.g. MoM), and the parsed dataset (Arguments).
    output: A per-period table (CSV format or Object) detailing the result and the exact formula used for each row.
    error_handling: Refuses to compute if growth_type is missing, or if nulls are present in the target subset (flags nulls instead of computing).
