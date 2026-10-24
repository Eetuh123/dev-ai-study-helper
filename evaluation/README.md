# Evaluation

The project was evaluated through retrieval checks, automated input
validation tests, a model comparison, and manual application testing.

## Files

- `test_cases.json`: test cases covering successful, difficult,
  and invalid-input scenarios.
- `evaluation_results.md`: recorded results, observations,
  and limitations.
- `model_comparison/`: saved model comparison outputs.

## Automated RAG validation

Run from the project root:

```bash
python -m pytest tests/test_rag_validation.py -v
```

These tests check that unknown concept IDs and non-positive result
counts are rejected. They do not measure retrieval relevance or
generated content quality.

To run the full automated test suite:

```bash
python -m pytest
```

## Retrieval checks

After building the local Chroma index, run:

```bash
python scripts/search_books.py "ketjusääntö"
```

Review whether the returned text explains the requested topic and
includes source references. Finding the correct chapter alone does
not guarantee that the retrieved material is suitable for the student.

## Model comparison

Run:

```bash
python scripts/compare_models.py
```

The comparison uses the same five mathematics questions and retrieved
source material for llama3.2, qwen3.5:4b, and qwen3.5:9b.

Answers are reviewed for mathematical correctness and explanation
clarity. Response times are measured by the script.

The models must be available locally through Ollama. Results and
limitations are documented in evaluation_results.md.

## Manual application testing

Manual checks cover lesson generation, source references, quiz
feedback, retrying with new questions, and progress persistence
after restarting the application.

Record observed results in evaluation_results.md. Keep preliminary
results separate from later tests when the model or implementation
has changed.