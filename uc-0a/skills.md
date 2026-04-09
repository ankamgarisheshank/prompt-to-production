skills:
  - name: classify_complaint
    description: Classifies a single citizen complaint row into a standardized category, assigns priority, provides a citation reason, and flags ambiguity.
    input: A single citizen complaint row including text description (String).
    output: A populated schema containing category (String), priority (String), reason (String), and flag (String).
    error_handling: Handles ambiguous complaints by setting category to "Other" and flag to "NEEDS_REVIEW".

  - name: batch_classify
    description: Reads an input CSV of complaints, processes each row via classify_complaint, and outputs the results to a new CSV file.
    input: Filepath to an input CSV (String).
    output: A generated CSV file containing classified results.
    error_handling: Notifies the user if the input CSV format is invalid or file doesn't exist, skipping invalid rows instead of halting execution.
