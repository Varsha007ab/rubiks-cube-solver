# Implementation Note

## Purpose

This note explains the relationship between the academic project report/presentation and the Python implementation included in this repository.

## Current Python implementation

The file `src/rubiks_cube_solver.py` contains the computer-vision implementation provided with the project. It performs the following stages:

1. Loads the six cube-face images.
2. Detects a 3×3 sticker grid using OpenCV.
3. Converts image regions to HSV.
4. Classifies sticker colors using reference HSV values.
5. Calculates confidence values for detected colors.
6. Uses center stickers to map detected colors to cube faces.
7. Validates the cube configuration.
8. Converts the detected state into a Kociemba facelet string.
9. Calls the `kociemba` solver to generate a solution.
10. Prints the solution and a step-by-step explanation of each move.
11. Saves annotated and preview images in `debug_output/`.

## DSA material in the report

The accompanying academic report and presentation discuss Rubik's Cube as a state-space search problem and present Iterative Deepening A* (IDA*) and heuristic search concepts.

The report covers:

- 54-sticker cube-state representation
- Graph/state-space search
- IDA*
- Heuristic functions
- Recursive depth-first search
- Move generation
- Time and space complexity
- Comparisons with BFS, DFS, A*, and IDDFS

## Important distinction

The report/presentation describe IDA* as the primary DSA approach, while the Python implementation currently uses the external `kociemba` package for the final solving stage.

This distinction is documented intentionally so that the repository accurately represents the code that is actually included.

## Future alignment

A future version can implement the IDA* solver directly inside the repository, making the implementation fully aligned with the algorithmic approach described in the academic report.
