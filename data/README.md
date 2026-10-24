# Project Data

## Concept map

`concepts.json` contains 74 mathematical skills, including their
names, descriptions, direct prerequisites, and source references.

The skills cover algebra, functions, trigonometry, limits,
and differentiation.

## Learning materials

The application uses material from three OpenStax textbooks:

- College Algebra 2e
- Precalculus 2e
- Calculus Volume 1

Downloaded books and converted files are stored locally under
`data/books/` and are excluded from Git.

## Retrieval data

`data/rag/` contains generated text chunks and other local retrieval
files. These files are excluded from Git.

The Chroma database is generated locally. On Windows, the current
configuration stores it under
`%LOCALAPPDATA%\dev-ai-project\chroma`.

See the main README for book download instructions, conversion,
and Chroma indexing.

## Learning progress

`progress.json` stores local learning progress between sessions.