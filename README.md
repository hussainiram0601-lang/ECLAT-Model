# Market Basket Analysis using the ECLAT Algorithm 🛒

This repository implements **Market Basket Analysis** engineered through the **ECLAT (Equivalence Class Clustering and bottom-up Lattice Traversal)** framework. The pipeline mines an unsupervised transactional database consisting of 7,501 retail entries to pinpoint frequent itemsets and product pairings.

## 🧠 Why ECLAT?
While both Apriori and ECLAT are premier Unsupervised Learning techniques for Association Rule Mining, **ECLAT** offers unique advantages:
* **Item-Centric Depth-First Search (DFS)**: ECLAT utilizes a vertical database format to map item intersections instead of repeatedly checking horizontal rows.
* **Single Database Scan**: It calculates itemset frequency over an active layout footprint rather than iteratively rescanning raw transaction indexes.
* **Efficiency**: Provides superior execution velocities on mid-sized tabular arrays where memory footprints are compact.

## 🛠️ Data Pipeline Architecture

### 1. Transaction Mapping
* Cleansed and aggregated raw text records containing variant basket lengths (up to 20 products per unique shopper).
* Standardized all inputs into a clean string list sequence spanning `range(0, 7501)`.

### 2. Frequent Itemset Generation
* Set execution boundaries to filter out arbitrary non-frequent combinations:
  * `min_support = 0.003` (Ensuring items are present in a meaningful distribution density relative to overall transactions).
  * `min_length = 2` / `max_length = 2` (Configured to accurately isolate precise binary item combinations).

### 3. Discovered High-Support Pairings
The vertical evaluation structure successfully isolated critical operational pairs, uncovering valuable item sets such as:
* **Set**: `{Light Cream, Chicken}` ➡️ *Support*: `0.0045`
* **Set**: `{Mushroom Cream Sauce, Escalope}` ➡️ *Support*: `0.0057`
* **Set**: `{Pasta, Escalope}` ➡️ *Support*: `0.0058`

## 💻 Tech Stack
* **Language**: Python 3
* **Environment**: Jupyter Notebook / Google Colab
* **Libraries**: `apyori` (Association Mining Framework), `pandas`, `numpy`
# ECLAT-Model
