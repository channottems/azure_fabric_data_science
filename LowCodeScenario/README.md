# Low-Code Data Science End-to-End Scenario: Churn Prediction

Welcome to the **Low-Code Data Science End-to-End Scenario** tutorial series! This tutorial walks you through the steps of data ingestion, data cleaning, model training, and prediction using **Microsoft Fabric** with a low-code approach. The goal is to predict customer churn using the data of bank customers.

### **Tutorial Overview**:

* **Ingest Data**: Import data from external sources to your lakehouse.
* **Clean & Prepare Data**: Clean and prepare the data using low-code tools like Data Wrangler.
* **Train & Predict**: Train a machine learning model to predict customer churn.

---

## 📚 Table of Contents

1. [Ingest Data](#-ingest-data)
2. [Clean and Prepare Data](#-clean-and-prepare-data)
3. [Train and Predict](#-train-and-predict)

---

## 🧑‍💻 Ingest Data

Follow these steps to ingest data into the lakehouse:

1. **Create a New Lakehouse**:

   * Name: `churnLowCodeLakeHouse`
2. **Create a Data Pipeline**:

   * Go to **LakeHouse** > **Get Data** > **New Data Pipeline**.
   * Name: `CopyData` and click **Create**.
3. **Open Assistant Low-Code**:

   * The assistant should open automatically, or you can select it from the list.
4. **Configure Data Source**:

   * **Source Type**: `HTTP`
   * **Link**: [Churn Data CSV](https://synapseaisolutionsa.blob.core.windows.net/public/bankcustomerchurn/churn.csv) (or use this alternative: [Churn Data CSV](https://raw.githubusercontent.com/KC2016/churn-modelling-Kaggle/main/data/Churn_Modelling.csv))
5. **Create New Connection**:

   * Connection Name: `churnNoCodeConnection`
   * Configure: Choose **Comma** as delimiter and set the first row as header, then click **Next**.
6. **Set Folder and File Path**:

   * Folder Path: `raw/`
   * File Name: `churn.csv`
7. **Start Data Transfer**:

   * Enable **Start data transfer immediately**.
   * Click **Save & Run**.
8. **Wait for the Pipeline to Finish**.
9. **Refresh Lakehouse**:

   * Go to the lakehouse and refresh to see the data.

---

## 🧹 Clean and Prepare Data

Now, let's clean and prepare the data for modeling:

1. **Open Notebook**:

   * Go to **LakeHouse** > **Open Notebook** > **New Notebook**.
2. **Load the Data**:

   * In the notebook, navigate to `raw` > select `churn.csv` > Click `…` > **Load Data** > Select **Spark**.
3. **Check Data Types**:

   * Run the notebook and observe that the data type is `string`.
4. **Use Copilot to Adjust Data Types**:

   * Use **Copilot**: "Load the data by inferring the correct data type" or "Guess data type when loading".
   * Accept and run it. The `Exited` column should now be corrected to `int`.
5. **Clean Data with Data Wrangler**:

   * In **Data Wrangler**, work with the dataframe (`df`).

     * **Drop Duplicate Rows**: Drop columns `RowNb` and `CustomerID`, then apply.
     * **Remove Missing Values**: Drop rows with missing values.
     * **Drop Unnecessary Columns**: Drop `RowNb`, `CustomerID`, and `Surname`, then apply.
6. **Add Code to Notebook**:

   * Finish with **+ Add code to notebook** > Click **Add** > Run the code.
7. **Visualize the Data**:

   * Use `display(df_clean)` to visualize and generate charts:

     * **Box Plot**: Visualize `EstimatedSalary` on the y-axis.
     * **Column Chart**: Show `Geography` vs. `Exited` (count by `Exited`).
     * **Column Chart**: Show `Age` distribution vs. `Exited`.
8. **Apply Quantile Cuts (qcut)**:

   * In **Data Wrangler**:

     * Create `NewTenure` by dividing `Tenure` by `Age`.
     * Use `qcut` to bin **CreditScore** into 6 quantiles (`NewCreditsScore`).
     * Use `qcut` to bin **Age** into 8 quantiles (`NewAgeScore`).
     * Apply **qcut** on `Balance` with 5 bins (`NewBalanceScore`).
     * Apply **qcut** on `EstimatedSalary` into 10 bins (`NewEstSalaryScore`).
9. **One-Hot Encoding**:

   * One-hot encode `Gender` and `Geography`.
10. **Save Clean Data**:

* Use **Copilot** to save the cleaned dataframe (`df_clean_1`) into the lakehouse as a Delta Table named `df_clean`.

11. **Refresh Lakehouse**:

* After saving, refresh the lakehouse and confirm the table `df_clean` appears.

---

## 🤖 Train and Predict

Finally, let's train the model and make predictions:

1. **Create ML Model**:

   * In the lakehouse, click **+ New Item** > **ML Model**.
   * Name: `predict_churn`.
2. **Start AutoML**:

   * Select **AutoML** for training the model.
3. **Connect to the Lakehouse**:

   * Ensure you're connected to the correct lakehouse.
4. **Choose Model Type**:

   * Select **Binary Classification**.
5. **Select Data**:

   * Choose the **df\_clean** dataset.
6. **Select Prediction Column**:

   * Set **Exited** as the prediction column.
7. **Run Prediction**:

   * Open the `predict_churn` notebook and run all cells to train the model and predict churn.
8. **View the Model Split**:

   * The AutoML process will automatically split the data into training and testing sets.
9. **Check Predictions**:

   * Refresh the lakehouse and check for the prediction results in the table.
10. **View Experiment Results**:

* Go to the workspace > **Experiments** to see model statistics.

11. **Analyze Learner**:

* Review the type of model used in the **Learner** tab.

---

## 🚀 Next Steps

Now that you've ingested, cleaned, and trained your model, you're ready to dive deeper into the data and explore additional predictive insights. You can further refine the model and integrate with other tools like **Power BI** for visualizing predictions.
