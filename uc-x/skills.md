skills:
  - name: retrieve_documents
    description: Loads all specified HR, IT, and Finance policy files and indexes them by document name and section number.
    input: List of filepaths to the policy text documents (List of Strings).
    output: An indexed dictionary mapping document names and section numbers to text contents (Dictionary).
    error_handling: System halts execution if any specified policy document is inaccessible or missing.

  - name: answer_question
    description: Searches indexed documents to provide a single-source answer with a citation, or returns a strict refusal if not found.
    input: The user's question (String) and the loaded document index (Dictionary).
    output: A precise text answer containing either the strict refusal template or the specific answer with document name and section citation (String).
    error_handling: Handles ambiguous or unavailable information by outputting the strict refusal template verbatim without hallucinating.
