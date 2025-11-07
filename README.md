# 📊 Sorting Algorithm Comparison Visualizer

This project is a single-file, interactive HTML application that provides a side-by-side visual comparison of 10 common sorting algorithms. It allows users to observe how each algorithm handles the **exact same initial data set** simultaneously, making it an excellent educational tool for understanding their operational mechanics and performance differences.

---

## ✨ Features

* **10 Algorithms Compared:** Visually run Bubble Sort, Selection Sort, Insertion Sort, Merge Sort, Quick Sort, Heap Sort, Counting Sort, Radix Sort, Bucket Sort, and Shell Sort.
* **Real-Time Visualization:** Elements are highlighted as they are **compared** (Red), **swapped/moved** (Yellow), or placed in their **final sorted position** (Green).
* **Customizable Settings:** Adjust the array size (5 to 100 elements) and the visualization speed (animation delay).
* **Single-File Simplicity:** The entire application is contained in one `index.html` file, requiring no local server or dependencies other than a web browser.

---

## 🚀 Getting Started

Follow these simple steps to run the visualizer locally.

### 1. Save the Code

The entire application is in a single file.

1.  Create a new folder for your project (e.g., `sorting-visualizer`).
2.  Inside that folder, create a new file named `index.html`.
3.  Copy and paste the entire provided HTML code (from the previous response) into this `index.html` file.

### 2. Run the Visualizer

Simply open the file in your web browser.

* Navigate to the folder and **double-click** `index.html`.

The visualizer should open immediately, ready to run.

---

## 🧠 How to Use

1.  **Adjust Array Size:** Use the **Array Size** slider to set the number of elements (bars) for the comparison.
2.  **Set Speed:** Use the **Speed** slider to control the delay between steps. A higher number means a slower, clearer animation.
3.  **Start Comparison:** Click the **Start Comparison** button.
4.  **Observe:** Watch the 10 grids simultaneously. Notice the difference in the number of swaps, comparisons, and overall complexity, especially between $O(N^2)$ algorithms (like Bubble Sort) and $O(N \log N)$ or linear-time sorts (like Merge Sort or Radix Sort).

---

## 🛠️ Technology Stack

This project uses minimal, web-standard technologies for maximum accessibility:

* **HTML5:** Structure.
* **Vanilla JavaScript (ES6+):** Core logic, array generation, and the asynchronous sorting functions.
* **Canvas API:** Used for highly performant, step-by-step rendering of the bar charts.
* **Tailwind CSS (via CDN):** Used for simple, modern styling and responsive layout.

---

## 💡 Algorithm Complexity Quick Reference

The visualizer clearly demonstrates the differences in performance between these complexity classes:

| Algorithm | Best Case | Average Case | Worst Case | Space Complexity |
| :--- | :--- | :--- | :--- | :--- |
| **Quick Sort** | $O(N \log N)$ | $O(N \log N)$ | $O(N^2)$ | $O(\log N)$ |
| **Merge Sort** | $O(N \log N)$ | $O(N \log N)$ | $O(N \log N)$ | $O(N)$ |
| **Heap Sort** | $O(N \log N)$ | $O(N \log N)$ | $O(N \log N)$ | $O(1)$ |
| **Shell Sort** | $O(N \log N)$ | $O(N (\log N)^2)$ | $O(N^2)$ | $O(1)$ |
| **Insertion Sort** | $O(N)$ | $O(N^2)$ | $O(N^2)$ | $O(1)$ |
| **Bubble Sort** | $O(N)$ | $O(N^2)$ | $O(N^2)$ | $O(1)$ |
| **Selection Sort** | $O(N^2)$ | $O(N^2)$ | $O(N^2)$ | $O(1)$ |
| **Counting Sort** | $O(N+K)$ | $O(N+K)$ | $O(N+K)$ | $O(N+K)$ |
| **Radix Sort** | $O(NK)$ | $O(NK)$ | $O(NK)$ | $O(N+K)$ |
| **Bucket Sort** | $O(N+K)$ | $O(N)$ | $O(N^2)$ | $O(N+K)$ |
*Note: $N$ is the number of elements, $K$ is the range of input values or the number of digits.*
