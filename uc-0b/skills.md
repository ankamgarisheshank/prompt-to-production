# skills.md
# INSTRUCTIONS: Generate a draft by prompting AI, then manually refine this file.
# Delete these comments before committing.

skills:
  - name: retrieve_policy
    description: Loads a text policy file and returns the content as structured, numbered sections.
    input: Filepath to the policy document (String).
    output: A structured object mapping clause numbers to their core text (e.g., Dictionary or List of Sections).
    error_handling: Raises an error if the file is missing or unreadable, immediately halting the process.

  - name: summarize_policy
    description: Takes structured sections from the policy and produces a compliant summary with clause references, ensuring no obligations are dropped.
    input: Structured numbered sections from retrieve_policy (Dictionary/List).
    output: A text summary of the policy with all critical clauses preserved (String).
    error_handling: "If a clause cannot be summarized without losing meaning, quotes it verbatim and flags it for review."
