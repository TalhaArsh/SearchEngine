# SearchEngine

## Table of Contents
1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Dependencies](#dependencies)
4. [File Structure](#file-structure)
5. [How to Run](#how-to-run)
6. [Usage](#usage)
7. [Code Breakdown](#code-breakdown)
8. [Contributing](#contributing)

---

## Project Overview

This project implements a simple **Search Engine** using a **Trie** data structure. It indexes documents stored as text files in a specified directory and allows users to search for terms across the files. It supports:
- Adding terms to the Trie from documents.
- Searching terms using AND/OR operators.
- Ranking results by the frequency of term occurrences in the documents.
- Document navigation (forward/backward) during search.

---

## Features

- **Document Indexing:** Indexes text files and builds a Trie for efficient search.
- **Term Frequency Calculation:** Tracks the frequency of terms in each document.
- **Search with Cache:** Search results are cached for faster future queries.
- **Document Navigation:** Navigate between documents (forward and backward).
- **AND/OR Operator Search:** Supports advanced search with logical operators.

---

## Dependencies

The project relies on basic C++ libraries and does not require any external dependencies:
- `<iostream>`: Input and Output handling.
- `<unordered_map>`: Efficient hash map for Trie children.
- `<vector>`: Dynamic arrays for storing document IDs.
- `<list>`: Doubly-linked list for managing adjacency lists in vertices.
- `<fstream>`: File I/O handling.
- `<algorithm>`: Utility functions like `transform` for string manipulation.
- `<sstream>`: String stream for parsing the query input.
- `<stack>`: Stack to store document navigation history.
- `<io.h>`: Directory handling for reading files.

---

## File Structure

```
SearchEngine/
├── main.cpp         # Core search engine code
├── README.md        # Documentation file (this file)
├── DSA FILES/       # Directory containing text files (documents to index)
│   └── *.txt        # Your document files go here (use numbered file names, e.g., "document1.txt")
```

---

## How to Run

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your_username/SearchEngine.git
   cd SearchEngine
   ```

2. **Set up your documents:**
   Place all your text files in the `DSA FILES` folder or any other directory of your choice. Ensure that the text file names include numbers for extracting document IDs (e.g., "document1.txt").

3. **Compile the Program:**
   Use a C++ compiler like `g++` to compile the code. Example:
   ```bash
   g++ -o search_engine main.cpp
   ```

4. **Run the Program:**
   ```bash
   ./search_engine
   ```

---

## Usage

- **Build Index:** The program automatically builds an index from all the `.txt` files in the specified directory.
- **Search Query:** Enter search queries to find document IDs containing the term(s). Use AND/OR operators for combined searches.
  Example queries:
  ```
  Search term: 'data'
  Search term: 'data AND structures'
  ```
- **View Documents:** After searching, you can enter a document ID to display the document content. Use the following commands to navigate:
  - **b**: Go back to the previous document.
  - **f**: Move forward to the next document.
  - **e**: Exit the program.

---

## Code Breakdown

### `vertexNode`
Represents a node in the document graph with connections to other documents. Each document (vertex) has:
- **DocID:** Document ID.
- **connection:** List of connections to other documents.

### `DocInfo`
Stores information about each document, including:
- **frequency:** Frequency of the search term.
- **filePath:** Path to the document.

### `TrieNode`
Each node in the Trie contains:
- **children:** Child nodes for each character.
- **docFrequency:** Frequency of a term in each document.
- **adjacentVertices:** Connections to other vertices (documents).
- **isEndOfWord:** Boolean to indicate the end of a word.

### `SearchEngine`
Core class of the search engine. Handles:
- **Building Index:** Parses text files and adds terms to the Trie.
- **Search:** Provides search functionalities with AND/OR operators.
- **Document Navigation:** Supports backward/forward navigation through visited documents.

---

## Contributing

Feel free to contribute to the project by submitting pull requests or reporting issues. Make sure to follow these guidelines:
1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Commit your changes and push them to your branch.
4. Open a pull request with a clear description of your changes.


