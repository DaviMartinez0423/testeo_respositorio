<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Videogames Data Streaming</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 20px;
        }
        .container {
            text-align: center;
        }
        .flex-container {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 20px;
        }
        .flex-container img {
            width: 180px;
            margin: 0 10px;
        }
        pre {
            background-color: #000000;
            color: #FFFFFF;
            padding: 10px;
            border: 1px solid #ccc;
            font-size: 14px;
            overflow-x: auto;
        }
        h2, h3 {
            margin-top: 30px;
        }
        ul {
            list-style-type: none;
            padding-left: 0;
        }
        li {
            margin-bottom: 10px;
        }
        a {
            color: #007bff;
            text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="flex-container">
            <img src="./public/Kafka_logo.png" alt="Kafka">
            <img src="./public/airflow_logo.png" alt="Airflow">
        </div>
        <h1>⚙️ Videogames Data Streaming ⚙️</h1>
        <p>Welcome to the continuation branch of our project. This branch focuses on processing and managing data obtained by combining a clean DataFrame and a dimensional model using the Apache Kafka and Apache Airflow platforms. This work is an extension of the efforts in the previous branches, where data cleaning (EDA) tasks were performed and the dimensional model was defined.</p>
        <p>In this project, the following platforms are utilized:</p>
        <ul>
            <li>Apache Kafka</li>
            <li>Apache Airflow</li>
            <li>Docker</li>
        </ul>
		    <h2>System Requirements 🖥️</h2>
    <h3>Docker:</h3>
    <ul>
        <li><strong>Operating System:</strong> Compatible with Windows, macOS, and Linux.</li>
        <li><strong>Processor:</strong> Should be 64-bit.</li>
        <li><strong>RAM:</strong> At least 4 GB is recommended.</li>
        <li><strong>Virtualization:</strong> Enable virtualization in the BIOS (such as "Intel VT-x" or "AMD-V").</li>
    </ul>
    <h3>Apache Kafka:</h3>
    <ul>
        <li><strong>64-bit Processor.</strong></li>
        <li><strong>RAM:</strong> At least 4 GB is recommended.</li>
        <li><strong>ZooKeeper:</strong> Up to version 2.8.0, Kafka relied on ZooKeeper for coordination. However, starting from version 2.8.0, Kafka supports a mode without ZooKeeper dependency.</li>
        <li><strong>Docker:</strong> Docker images for Kafka can be used.</li>
    </ul>
    <h3>Apache Airflow:</h3>
    <ul>
        <li><strong>Python:</strong> Python must be installed on your system.</li>
        <li><strong>RAM:</strong> At least 2 GB is recommended.</li>
        <li><strong>Operating System:</strong> Compatible with Windows, macOS, and Linux.</li>
    </ul>
        <p><strong>If you want to run the project on your computer, please make sure that your device is compatible with these applications. If it is not, I strongly recommend that you do not run this repository.</strong></p>
    </div>

    <h2>Project Structure 📃</h2>
    <p>The structure of the directories and files is as follows:</p>
    <pre>
 . <!-- Directory Structure -->
├── .gitignore
├── README.md
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
├── .vscode
│   └── settings.json
├── dags
│   ├── __init__.py
│   ├── dag_decorators.py
│   ├── etl.py
│   └── main.py
├── data
│   └── ...
├── docs
│   ├── Dashboard_proyecto.pdf
│   ├── ETL_documentation.pdf
│   └── Games_dashboard.pdf
├── notebooks
│   ├── eda_001.ipynb
│   ├── eda_002.ipynb
│   ├── eda_003.ipynb
│   └── eda_004.ipynb
├── pj3
│   └── ...
├── public
│   ├── airflow_logo.png
│   ├── kafka_logo.png
│   └── libraries.png
└── src
    └── etl.py
    </pre>
    <h2>Folders 📁</h2>
    <ul>
        <li><strong>dags 📑:</strong> Contains the files that will be used by the Airflow service.</li>
        <li><strong>data 📊:</strong> Contains .csv files with the data that will be used during the project.</li>
        <li><strong>docs 📙:</strong> Contains the documentation of the whole project, some of them talk about other branches, so take a look at them if you are interested.</li>
        <li><strong>notebooks 📚:</strong> Contains the Jupyter notebooks with the project's performance.</li>
        <li><strong>src 📂:</strong> Contains the ETL file that has the project's performance done in the Jupyter notebooks, but in only one Python file.</li>
    </ul>
    <p>We also have other files in the root that are key to the execution of the project, i.e., without these files, the project will not run correctly.</p>

    <h2>Installation Requirements ✔️</h2>
    <p>The required libraries are listed in the file 'requirements.txt'. Also, this file must be used to install the libraries using this command:</p>
    <pre>
        pip install -r requirements.txt
    </pre>
    <p>If installed successfully, you should have the following libraries installed:</p>
    <img src="./public/libraries.png" alt="Installed Libraries" style="max-width: 100%;">

    <h2>Project Execution 🚀</h2>
    <ol>
        <li>The repository must be cloned using this command:</li>
        <pre>
            git clone --corte3 https://github.com/juancbuitrago/ETL-Project.git
        </pre>
        <li>Enter the project with this command (you must run this inside the folder where you are cloning the repository):</li>
        <pre>
            cd your_folder
        </pre>
        <li>Open a command line and execute the following command to raise the Docker service:</li>
        <pre>
            docker compose up -d
        </pre>
        <li>Enter the airflow web server: <a href="http://localhost:8080">http://localhost:8080</a>. Execute the workflow</li>
        <li>In the same command line, execute this command to access the container and create the topic:</li>
        <pre>
            docker exec -it kafka-test bash
        </pre>
        <pre>
            kafka-topics --bootstrap-server kafka-test:9092 --create --topic games_stream
        </pre>
        <li>Open a new terminal, (preferably bash) and execute these commands to access into the folder with kafka producer and execute it:</li>
        <pre>
            cd dags
        </pre>
        <pre>
            python producer.py
        </pre>
        <li>With the producer running, execute the kafka consumer in the same folder using this command:</li>
        <pre>
            python consumer.py
        </pre>
    </ol>

    <h2>Contact 📧</h2>
    <p>If you have any questions or need further assistance, feel free to contact us:</p>
    <ul>
        <li><a href="mailto:dayanna.suarez@uao.edu.co">dayanna.suarez@uao.edu.co</a></li>
        <li><a href="mailto:david_fel.martinez@uao.edu.co">david_fel.martinez@uao.edu.co</a></li>
        <li><a href="mailto:juan_c.buitrago@uao.edu.co">juan_c.buitrago@uao.edu.co</a></li>
    </ul>
</body>
</html>
