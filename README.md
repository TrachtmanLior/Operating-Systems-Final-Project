# OS Final Project: MST, Strategy/Factory, Client-Server, Threads, and Valgrind

## 📖 Overview

This project is a comprehensive implementation that combines several operating systems concepts:

- **Minimal Spanning Tree (MST)** problem on a weighted, directed graph.
- Utilization of multiple **MST algorithms** (Borůvka, Prim, Kruskal, Tarjan).
- **Design Patterns**: Strategy/Factory for MST algorithm selection.
- **Client-Server Architecture**: Handling multiple concurrent clients via TCP.
- **Threads**: Implementation of the Leader-Follower thread pool pattern and Active Object.
- **Valgrind Analysis**: Memory management and concurrency checks using tools like `memcheck`, `helgrind`, and `cachegrind`.
- **Code Coverage**: Comprehensive testing to ensure coverage of all functionalities.

---

## 🛠️ Features

### MST Algorithms
- Implements Borůvka, Prim, Kruskal, and Tarjan algorithms for MST.
- Calculates:
  - Total weight of the MST.
  - Longest and shortest distances between vertices.
  - Average distance between edges in the MST.

### Server Functionality
- Accepts graphs, updates, and MST requests via TCP.
- Processes requests concurrently using threads with mutex protection.
- Supports multiple clients simultaneously.

### Profiling and Debugging
- Performance profiling with `gprof`.
- Memory and concurrency checks using `valgrind` tools.
- Pipeline-based processing with Active Object implementation.
- Leader-Follower thread pool for efficient task distribution.

---

## 📂 Project Structure

- **`Graph.cpp` / `Graph.hpp`**: Core graph data structure implementation.
- **`MSTSolver.cpp` / `MSTSolver.hpp`**: Implements the MST algorithms.
- **`MSTFactory.cpp` / `MSTFactory.hpp`**: Factory pattern for selecting MST strategies.
- **`Server.cpp`**: Handles client-server communication and task distribution.
- **`ThreadPool.cpp` / `ThreadPool.hpp`**: Implements the Leader-Follower thread pool pattern for task distribution.
- **`ThreadPoolServer.cpp`**: Server implementation utilizing the thread pool.
- **`Profiling.cpp`**: Profiling and performance measurement.
- **`Test.cpp`**: Unit tests for validating project functionality.
- **`makefile`**: Build script for compiling the project.
- **`OS_Project_Assignment.pdf`**: Detailed project description and requirements.

---

## 🧪 Testing and Code Coverage

- Unit tests ensure functionality of all modules.
- Use `gcov` for code coverage analysis:
  ```bash
  gcov -b *.cpp
  ```

---

## 🌟 Key Features to Explore

- Dynamic MST algorithm selection using the Factory pattern.
- Efficient graph processing with Leader-Follower thread pool.
- Robust memory and concurrency management verified by Valgrind tools.
- Modular design for extensibility and maintainability.

---

## 🚀 How to Run

1. **Compile the Project**:
   ```bash
   make all
   ```

2. **Run the Server**:
   ```bash
   ./server
   ```

3. **Client Interaction**:
   - Use any TCP client to connect to the server.
   - Send graph updates or MST requests.

4. **Profiling**:
   Run the application with profiling enabled:
   ```bash
   gprof ./server gmon.out > profiling_results.txt
   ```

5. **Valgrind Analysis**:
   Check memory leaks:
   ```bash
   valgrind --tool=memcheck ./server
   ```
   Check thread concurrency:
   ```bash
   valgrind --tool=helgrind ./server
   ```

