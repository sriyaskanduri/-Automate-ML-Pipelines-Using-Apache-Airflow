readme: |
  # Iris Classification with KNN using Apache Airflow

  This project demonstrates a modular machine learning workflow for Iris flower classification using the **K-Nearest Neighbors (KNN)** algorithm. The workflow is built using **Apache Airflow**, and is broken down into three sequential tasks (DAGs) for data loading, preprocessing, and model training/evaluation.

  ---

  ## 📌 Project Structure

  - **train_iris_model_1**  
    Loads the Iris dataset, encodes class labels numerically, and shares the cleaned data with the next task via Airflow XCom.

  - **train_iris_model_2**  
    Splits the dataset into training and testing sets, and pushes them to XCom.

  - **train_iris_model_3**  
    Implements the KNN algorithm manually to make predictions and prints the accuracy score.

  ---


Each task uses `xcom_push` and `xcom_pull` to pass data between stages.

---

## 🧠 Concepts Used

- **Apache Airflow** – Orchestrates the ML pipeline.
- **XCom (Cross Communication)** – Transfers intermediate data between tasks.
- **Manual KNN Algorithm** – Predicts classes using Euclidean distance and majority voting (k=3).
- **Iris Dataset** – Classic dataset with 3 flower species and 4 numerical features.

---

## 🚀 Getting Started

### Prerequisites

- Python ≥ 3.8
- Apache Airflow
- pandas, numpy

---

### Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/iris-airflow-knn.git
   cd iris-airflow-knn
   ```

2. **Install Dependencies**
   ```bash
   pip install apache-airflow pandas numpy
   ```

3. **Initialize Airflow**
   ```bash
   airflow db init
   airflow users create --username admin --password admin \
       --firstname admin --lastname user --role Admin --email admin@example.com
   ```

4. **Start Airflow Scheduler and Web Server**
   ```bash
   airflow scheduler
   airflow webserver --port 8080
   ```

5. **Trigger the DAG**
   - Open your browser and go to: [http://localhost:8080](http://localhost:8080)
   - Trigger the `iris_classification_models` DAG from the UI

---

## ✅ Example Output

After successful execution, the final task prints the accuracy of the KNN model on the test set: Accuracy: 0.9333


---

## 📁 Files

| File         | Description                        |
|--------------|------------------------------------|
| `iris_dag.py`| Airflow DAG for Iris KNN workflow  |
| `README.md`  | Project documentation              |

---

## 📚 References

- [Apache Airflow Docs](https://airflow.apache.org/docs/)
- [UCI Iris Dataset](https://archive.ics.uci.edu/ml/datasets/iris)




