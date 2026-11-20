# 🐚 Advanced Shell Scripting: API Automation and Data Pipelines

This project is a practical deep dive into **Advanced Shell Scripting**, focusing on building robust, efficient, and automated data pipelines. It simulates real-world DevOps and Data Engineering tasks by interacting with the **Pokémon RESTful API** directly from the command line.

We progress from simple API calls to complex operations involving **parallel processing**, **robust error handling**, and **structured data reporting** using classic UNIX tools.

---

## 🎯 Project Goals & Learning Objectives

The primary goal is to master essential command-line tools and shell scripting techniques to automate data extraction, transformation, and loading (ETL/ELT) processes.

By completing this project, you demonstrate proficiency in:

| Concept | Tools / Skills Demonstrated |
| :--- | :--- |
| **API Interaction** | Making **HTTP GET requests** using `curl` and checking HTTP status codes. |
| **JSON Processing** | Parsing, filtering, and extracting complex data structures using **`jq`**. |
| **Data Transformation** | Utilizing **`awk`**, **`sed`**, and **`grep`** for text filtering, substitution, and report generation. |
| **Robust Scripting** | Implementing **error handling**, **retry logic**, and status checking to ensure reliable scripts. |
| **Process Management** | Achieving parallelism and improving performance using **background processes (`&`)** and **`wait`**. |
| **Data Reporting** | Aggregating data from multiple JSON files and generating structured **CSV reports**. |

---

## 🛠️ Key Tools Used

| Tool | Primary Use in Project |
| :--- | :--- |
| **`curl`** | The main tool for fetching raw JSON data from the Pokémon API. |
| **`jq`** | Essential for parsing the JSON response and extracting specific fields (name, height, weight, type). |
| **`awk`** | Used for advanced text processing, formatting the CSV report, and calculating the **average height and weight**. |
| **`sed`** | Used for specific stream editing and text transformations. |
| **Shell Utilities** | Variables, loops (`for`), conditionals (`if`), functions, and process control (`&`, `wait`). |

---

## 🧪 Project Tasks Overview

The project is structured as a progressive series of scripts, each building on the last to create a complete data pipeline.

| Task File | Objective | Key Concepts Learned |
| :--- | :--- | :--- |
| **`apiAutomation-0x00`** | **Initial Request** | Basic `curl` usage, saving output to a file, basic error logging. |
| **`data_extraction_automation-0x01`** | **Data Transformation** | Advanced use of `jq`, `awk`, and `sed` to extract and reformat specific data fields into a human-readable string. |
| **`batchProcessing-0x02`** (v1) | **Batch Retrieval** | Looping through a list of items and implementing rate-limiting delays (`sleep`). |
| **`summaryData-0x03`** | **Data Reporting** | Reading multiple files, combining data, generating a **CSV report**, and performing calculations (averages) using `awk`. |
| **`batchProcessing-0x02`** (v2) | **Robust Handling** | Implementing a **retry mechanism** (up to 3 times) and robust status code checking for API requests. |
| **`batchProcessing-0x04`** | **Parallel Fetching** | Using **background processes (`&`)** and the **`wait`** command to fetch data concurrently, speeding up the pipeline. |

---

## 🚀 Usage

The scripts need `bash`, `curl` and `jq` (`sudo apt install jq`). They are already executable, so run them from `Advanced_shell/` in this order, because each one uses the files the previous one wrote:

```bash
cd Advanced_shell
./apiAutomation-0x00               # Pikachu -> data.json (failures go to errors.txt)
./data_extraction_automation-0x01  # "Pikachu is of type Electric, weighs 6kg, and is 0.4m tall."
./batchProcessing-0x02             # 5 Pokémon -> pokemon_data/, with 3 retries each
./summaryData-0x03                 # pokemon_data/ -> pokemon_report.csv + average height and weight
./batchProcessing-0x04             # the same 5 Pokémon fetched in parallel -> pokemon_data_parallel/
```

## 👤 Author

**Thubelihle Dlamini**, [GitHub](https://github.com/Dwaynemaster007) · [LinkedIn](https://linkedin.com/in/thubelihledlamini)

## 📄 License

[MIT](LICENSE)
