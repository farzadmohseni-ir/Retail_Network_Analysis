# Retail_Network_Analysis
Network analysis of retail data using Gephi. Identifies influential customers and complementary products through centrality metrics and modularity detection.

---

> This repository contains network-based analysis of retail datasets using Gephi.  
> Two scenarios are explored:
> - FM_1: Identifying influential customers
> - FM_2: Discovering complementary product patterns

---

## 🚀 Interactive Notebooks (Google Colab)

You can view and run the interactive Python notebooks for each scenario directly in Google Colab:

- [🧠 FM_1 - Influential Customer Network (WallMart)](https://colab.research.google.com/drive/1pfq0vwhJMSI7u_2EguONwA7YELJFAtEg?usp=sharing)
- [🛒 FM_2 - Complementary Product Network (Sales Transactions)](https://colab.research.google.com/drive/13ch_MMPjLBmgx7ZTrygeQ5X5LY5unsT-?usp=sharing)


---

## 🖼️ Sample Network Visualizations

### 🔷 FM_1 – Influential Customers Network (Q1)

Examples of user-product graphs created in Gephi showing central users and community structures:

![Q1 Screenshot 1](Q1/Answer%20output/Screenshot%202025-05-22%20095517.jpg)
![Q1 Screenshot 2](Q1/Answer%20output/Screenshot%202025-05-22%20104317.jpg)
![Q1 Screenshot 3](Q1/Answer%20output/Screenshot%202025-05-22%20124008.jpg)

---

### 🔶 FM_2 – Complementary Products Network (Q2)

Examples of co-purchase product graphs with modularity-based clustering and degree-based sizing:

![Q2 Screenshot 1](Q2/Answer%20output/screenshot_113109.png)
![Q2 Screenshot 2](Q2/Answer%20output/screenshot_114552.png)
![Q2 Screenshot 3](Q2/Answer%20output/screenshot_115009.png)


---

# 🎯 FM_1 - Influential Customer Network Analysis (WallMart Dataset)

## 📝 Question Description
**Question:** How can influential customers in the dissemination of product information be identified?  
**Question Code:** FM_1  
**Dataset:** `a1-ECDS8-WallMart`



## 📌 Scenario Objective

In this scenario, we use customer purchase data from the WallMart dataset to construct a directed network between products and users. The aim is to identify customers who frequently or diversely purchase products — indicating a higher likelihood of influence and engagement. These customers are often central nodes in the network.



## 🗂 Folder Structure

```
FM_1/
├── a1-ECDS8-WallMart/     # Raw and cleaned dataset (Excel/CSV)
├── Gephi/                 # Graph files (.gexf) for Gephi
├── Answer output/         # Visualizations (network screenshots)
├── Statistics/            # Node/edge metric tables
└── README.md              # This documentation file
```



## 🔍 Step-by-Step Workflow

### 1. **Data Preparation**
- Extract relevant columns: `User ID`, `Product ID`, `Purchase Count`
- Convert to edge list format CSV:

```
Source (Product ID), Target (User ID), Weight (Purchase Count)
```

### 2. **Graph Construction in Gephi**
- Open Gephi → File → Import Spreadsheet
- Choose **Directed Graph**
- Use `Product ID` as source nodes and `User ID` as target nodes
- Set edge weights using `Purchase Count`

### 3. **Network Analysis in Gephi**
- Run the following metrics:
  - **Weighted Indegree** (for users) to assess influence
  - **Modularity Class** to detect customer-product communities

### 4. **Visualization**
- Scale node size based on indegree
- Color nodes by modularity class
- Export network images to the `Answer output/` folder



## 📊 Metrics Used

| Metric            | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| Weighted Indegree | Number of purchases per user; identifies highly engaged/influential users  |
| Modularity Class  | Detects behavioral clusters or communities of customers and products       |



## 📤 Outputs

- List of high-indegree customers (potential influencers)
- Community clusters based on product-user relationships
- Network visualizations (`Answer output/`)
- Graph metrics summary (`Statistics/`)



## 🛠 Tools Used

- [Gephi](https://gephi.org) – for network analysis and visualization
- Microsoft Excel – for data cleaning and formatting



## 🎯 Use Cases

- Identify key customers for loyalty or referral programs
- Support targeted marketing efforts
- Provide a foundation for recommendation systems

---

# 🛒 FM_2 - Complementary Product Network Analysis (Sales Transaction Dataset)

## 📝 Question Description
**Question:** Which items are commonly purchased together?  
**Question Code:** FM_2  
**Dataset:** `a0-ECDS9-EcTransacts (Sales Transaction v.4a)`



## 📌 Scenario Objective

This scenario uses retail transaction data to identify products that are frequently purchased together. By constructing a co-occurrence network of products within transactions, we can detect complementary products and product groupings. These insights are useful for building recommendation systems and bundling strategies.



## 🗂 Folder Structure

```
FM_2/
├── a0-ECDS9-EcTransacts/     # Raw and cleaned transaction data
├── cleaned_Sales Transaction v.4a.xlsx  # Preprocessed item-transaction matrix
├── Gephi/                    # Graph files (.gexf) for Gephi
├── Answer output/            # Visualizations of product network
├── Statistics/               # Graph metrics (degree, modularity, etc.)
└── README.md                 # This documentation file
```



## 🔍 Step-by-Step Workflow

### 1. **Data Preparation**
- Group transaction records by `Transaction ID`
- For each transaction, extract all product pairs
- Calculate edge weight as:  
  ```
  Weight = min(Quantity of Product A, Quantity of Product B)
  ```
- Create edge list format CSV:

```
Source (Product A), Target (Product B), Weight (min quantity)
```

### 2. **Graph Construction in Gephi**
- Open Gephi → File → Import Spreadsheet
- Choose **Undirected Graph**
- Nodes: Products
- Edges: Between products purchased together in the same transaction
- Set edge weights based on minimum quantities

### 3. **Network Analysis in Gephi**
- Run the following metrics:
  - **Degree**: shows how many other products a product co-occurs with
  - **Modularity Class**: detects product clusters often bought together

### 4. **Visualization**
- Adjust node size using degree
- Color nodes based on modularity class
- Export visuals to the `Answer output/` folder



## 📊 Metrics Used

| Metric         | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| Degree         | Number of direct co-purchase links (product popularity in bundles)         |
| Modularity     | Groups of complementary products (community detection)                     |



## 📤 Outputs

- Network of frequently co-purchased products
- Identified product clusters for bundle offers
- Network graph images (`Answer output/`)
- Metric summaries (`Statistics/`)



## 🛠 Tools Used

- [Gephi](https://gephi.org) – for graph creation and analysis
- Microsoft Excel – for transaction grouping and pair generation



## 🎯 Use Cases

- Create intelligent product recommendation systems
- Design product bundles to increase cross-selling
- Optimize store layout and product placement


