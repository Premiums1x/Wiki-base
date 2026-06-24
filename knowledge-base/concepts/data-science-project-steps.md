---
concept: data-science-project-steps
entity_type: technique
aliases: []
sources: ["raw\\02-data-science-and-bigdata\\data_science_bigdata.md"]
confidence: high
created_at: 2026-06-24T09:42:38Z
---

## Definition
Data Science Project Steps refer to a structured process that caters to transforming raw data into insights and actionable outcomes through a series of coherent and well-defined stages. This process extends data-scientist-roles-in-data-lifecycle by ensuring that data scientists rigorously handle data from inception to final delivery of results.

## How it works
A standard data science project typically adheres to several defined steps:

1. **Data Ingestion:** This involves the collection of raw data from a variety of sources, such as APIs, web scrapes, databases, or log files. The initial collection is critical as it sets the foundation for subsequent analysis and modeling processes.

2. **Data Wrangling/Cleaning:** Following data ingestion, the data is usually unprocessed and requires significant cleaning to prepare it for analysis. Data scientists engage in activities like handling missing values, addressing outliers, and eliminating duplicate records. This step is crucial because it directly impacts the quality and reliability of the final outcomes. Cleaning and preparing data, which can consume up to 80% of the data scientist's time, builds on data-cleaning-strategies-and-techniques.

3. **Exploratory Data Analysis (EDA):** Utilizing statistical charts and graphs, data scientists delve into understanding the data's inherent structure, patterns, and relationships. EDA is not only about discovering the data's potential but also about gaining insights that can guide feature selection, model building, and hypothesis generation. Techniques such as scatter plots, histogram plots, and line charts enhance the clarity of data visualizations and are integral components of EDA frameworks.

4. **Feature Engineering:** This step involves crafting features from raw data to use for training models. This process might include engineering new features from the raw data itself or selecting the most relevant features from the available set. Feature engineering is a critical step that directly impacts the performance of the models. It often requires a deep understanding of both the data and the business context and is a process that heavily depends on model-selection-techniques for eventual model training.

5. **Model Training and Evaluation:** The data scientists choose from a range of machine learning algorithms for fitting the data. The performance of these models is assessed using validation methods like cross-validation, focusing on enhancing accuracy and robustness of the model.

## Variants
Given the diverse nature of data science projects, there are several variations to the basic lifecycle:

- **Automated Data Science Processes (ADSP):** This variant extends the manual processes involved in traditional data science projects by deploying automation tools and MLops methodologies. These provide systematic solutions for scaling up data science operations and allowing for faster iterations and wider collaboration among teams. ADSP is an implementation of a standardized data science pipeline.
  
- **Direct to Deployment Data Science:** Focused on reducing the time from ideation to deployment, this approach emphasizes precise and actionable models right from the start. It contrasts with the more exploratory nature of traditional data science, which may initially generate a range of models or hypotheses to test.

- **Semi-automated Data Management:** This approach implements a partially automated framework around the data science lifecycle, supporting data science teams with automatic or semi-automatic tools for large-scale data collection, processing, and model training.

## Trade-offs
While the steps in a data science project lifecycle are useful, various trade-offs arise:

- **Data Quality vs Processing Time:** Higher data quality often comes at the cost of longer processing times. Cleaning and preparing data meticulously may be intensive and time-consuming, and as such, there is a constant trade-off between spending additional time improving data quality versus moving quickly with the available data.
  
- **Quality vs Quantity of Data:** Deciding on the amount of data to work with also involves trade-offs. Higher quality data may require a smaller volume to produce valuable insights, while a larger volume of lower quality data might yield less accurate but broader insights. The choice largely depends on the specific goals of the project.
  
- **Exploration vs Directed Goals:** EDA can sometimes be seen as a less directed form of analysis compared to algorithms with specific targets. However, a thorough exploration phase often reveals unexpected patterns or outliers that directed methods would miss.