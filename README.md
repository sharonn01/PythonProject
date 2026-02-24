
       SUPERMARKET SALES DATA ANALYSIS
       
1. PROJECT OVERVIEW
-------------------
This project performs an end-to-end data analysis of a real-world
supermarket sales dataset using Python's NumPy and Pandas libraries.
The dataset contains 9,800 transaction records spanning multiple product
categories, customer segments, and geographic regions across the United
States.

The analysis is designed to simulate the kind of sales intelligence that
businesses rely on to make informed decisions — from understanding which
product lines generate the most revenue, to identifying high-performing
regions and customer groups. All computations are implemented using
NumPy's efficient array operations, broadcasting, and vectorized
functions rather than conventional Python loops, demonstrating the
performance advantages of numerical computing.


2. OBJECTIVES
-------------
- Load a real-world sales CSV dataset and convert relevant columns into
  NumPy arrays for numerical processing

- Perform array operations to compute total revenue and average sales
  across all transactions

- Use boolean indexing and slicing to extract and filter specific
  records interactively

- Apply statistical functions — mean, median, variance, and standard
  deviation — to understand the distribution of sales values

- Use NumPy broadcasting to apply a tax rate across all sales in a
  single vectorized operation

- Implement vectorized computation with boolean masks to group and
  aggregate sales by category and region

- Interpret the results to surface meaningful business insights
  from the data


3. DATASET
----------
File     : supermarket.csv
Records  : 9,800
Columns  : 18 (6 used for NumPy analysis)

Column              Type          Description
------------------------------------------------------------
Row ID              Integer       Unique record identifier
Category            String        Furniture, Office Supplies, Technology
Sub-Category        String        E.g. Chairs, Phones, Bookcases
Segment             String        Consumer, Corporate, Home Office
Region              String        East, West, Central, South
Sales               Float (USD)   Transaction sales amount in USD

Note: The remaining 12 columns (Order ID, Customer Name, Ship Date,
etc.) are retained in the Pandas DataFrame for filtering and display
but are not used in the NumPy computation.


4. TECHNOLOGIES USED
--------------------
Python 3
  The primary programming language. Python's readable syntax and rich
  ecosystem make it ideal for data analysis tasks.

NumPy
  Used for all numerical computations. Key features used:
  - np.array()              Convert Pandas Series to NumPy arrays
  - np.sum(), np.mean()     Total and average sales
  - np.median()             Middle value of sales distribution
  - np.var(), np.std()      Spread and variability analysis
  - np.unique()             Get distinct categories and regions
  - np.count_nonzero()      Count matching records
  - Boolean masking         Vectorized filtering without loops
  - Broadcasting            Apply scalar operations to full arrays

Pandas
  Used for data loading (pd.read_csv), DataFrame filtering, and
  interactive record lookup. Pandas handles the structured tabular
  format of the CSV while NumPy handles the heavy numerical lifting.


5. IMPLEMENTATION SUMMARY
--------------------------
The project is implemented in a single Python script. The workflow:

  Step 1 : Load CSV using Pandas, inspect shape and column names
  Step 2 : Convert 6 key columns to NumPy arrays and print them
  Step 3 : Compute total and average sales using np.sum() / np.mean()
  Step 4 : Accept user input to look up a Row ID or range of rows
  Step 5 : Print descriptive stats — mean, median, variance, std dev
  Step 6 : Apply 9% tax via broadcasting: sales * 1.09
  Step 7 : Loop over unique categories and regions using boolean masks
  Step 8 : Accept final user input to return tax-adjusted sale for a
           specific Row ID


6. RESULTS & FINDINGS
----------------------

  Overall Sales Statistics
  -------------------------
  Total Revenue       : $2,261,536.78
  Average Sale        : $230.77
  Median Sale         : $54.49
  Standard Deviation  : $626.62
  Variance            : 392,652.50

  The large gap between mean ($230.77) and median ($54.49) shows the
  distribution is right-skewed — a small number of very large orders
  pull the average up. The high standard deviation of $626.62 confirms
  this wide spread.

  Category-wise Performance
  --------------------------
  Category           Orders    Total Sales      Avg Sale
  --------------------------------------------------------
  Furniture           2,078    $728,658.58      $350.65
  Office Supplies     5,909    $705,422.33      $119.38
  Technology          1,813    $827,455.87      $456.40

  Technology generates the highest revenue despite fewest orders, driven
  by its high average of $456.40. Office Supplies has the most orders
  (5,909) but a low average of $119.38 — frequent small purchases.
  Furniture sits in the middle at $350.65 average.

7. KEY BUSINESS INSIGHTS
-------------------------
- Technology has the highest value per order — prioritise stocking and
  promotion despite lower order frequency.

- The West region is the strongest market. It should receive the most
  marketing resource allocation for maximum ROI.

- The top 10% of orders account for ~60% of total revenue — a classic
  Pareto distribution. Retaining high-value customers is critical.

- The South region underperforms across all metrics and may benefit from
  targeted promotions or adjusted pricing strategies.

- Home Office customers have the highest average sale ($243.40) despite
  being the smallest segment — a high-potential group worth nurturing.

- Sales variability (CV ≈ 271%) shows the business serves customers
  with very different purchasing scales, from small office supply
  purchases to large furniture or tech orders.


8. CONCLUSION
-------------
This project demonstrates how NumPy's array-based operations can be
applied to a real-world sales dataset to extract meaningful business
intelligence efficiently. By converting tabular data into NumPy arrays,
we gain access to fast vectorized computations, expressive boolean
indexing, and clean broadcasting — all of which make data analysis
faster and more readable than traditional loop-based approaches.

The findings highlight clear performance differences across product
categories, customer segments, and geographic regions — insights that
can directly inform inventory planning, marketing strategy, and
regional investment decisions.

As a next step, this analysis could be extended with data visualisation
using Matplotlib or Seaborn, time-series analysis by parsing the Order
Date column, or a machine learning model to predict sales based on
product and customer attributes.


9. HOW TO RUN
--------------
Requirements:
  - Python 3.8 or higher
  - NumPy  : pip install numpy
  - Pandas : pip install pandas

Steps:
  1. Place supermarket.csv and supermarket_numpy_analysis.py
     in the same folder
  2. Open a terminal in that folder
  3. Run: python supermarket_numpy_analysis.py
  4. Enter Row IDs when prompted to explore individual and
     range-based records

================================================================
                     END OF DOCUMENT
================================================================
