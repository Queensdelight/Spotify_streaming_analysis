# 🎵 Spotify Streaming Data Pipeline 

## **Overview**
This project is a real-time streaming data pipeline built using Kafka, SQLite, and Streamlit to analyze Spotify music trends. 
It allows real-time tracking of streamed songs, sentiment analysis, and genre distribution, and displays interactive dashboards.
A Kafka Producer `spotify_producer.py` streams Spotify data while a Kafka consumer `spotify_consumer.py` processes the data, calculates sentiment scores, and stores them in SQLite for real-time analysis.

## **Features**
- **Kafka-based Streaming Pipeline**: Streams data from a Spotify dataset in real time.  
- **SQLite Database Storage**: Processes and stores data dynamically.  
- **Sentiment Analysis**: Computes sentiment scores based on song characteristics.  
- **Interactive Dashboards**:  
   - `dashboard.py` **Top Songs, Genre Trends, Streaming Trends**   
   - `sentiment_dashboard.py` **Sentiment Analysis by Genre & Time** 
**Auto-Refreshing Dashboard**: Updates data every 5 seconds.  

## **Dependencies**
- **Python 3.11**
- **Kafka** (for real-time streaming)
- **SQLite** (for storing data)
- **Pandas** (for data processing)
- **Matplotlib** (for charts)
- **Streamlit** (for interactive dashboards)

## **Installation & Setup**
### **Clone the Repository**
```sh
git clone https://github.com/Queensdelight/Spotify_streaming_analysis.git
```
## Manage Local Project Virtual Environment

Follow the instructions in [MANAGE-VENV.md](https://github.com/denisecase/buzzline-01-case/blob/main/docs/MANAGE-VENV.md) to:
1. Create your .venv
2. Activate .venv
3. Install the required dependencies using requirements.txt.

## As Needed: Activate .venv and Install Packages

Run the following commands to activate our local project virtual environment 
and install the necessary packages. 
Wait for each command to finish before running the next command. 

## One-time Only: Create it 

Use the built in venv utility to create a local project virtual environment in a folder named .venv. 

Windows: 
```shell
py -3.11 -m venv .venv
```

Mac/Linux:
```zsh
python3 -3.11 -m venv .venv
```

Windows: 

```shell
.venv\Scripts\activate
py -m pip install --upgrade pip setuptools wheel
py -m pip install --upgrade -r requirements.txt
pip install -r requirements.txt
```

Mac/Linux: 

```zsh
source .venv/bin/activate
python3 -m pip install --upgrade pip setuptools wheel
python3 -m pip install --upgrade -r requirements.txt
```

Be patient. will end and a new .venv folder will appear.
This folder will become very large - we don't do anything with it directly, 
but Python will use this local virtual environment folder to hold a lot of
free code that we will use in our project. When done, .venv may be large. Allow time.

## Activate Every Time We Open a New Terminal 

Remember to always activate the .venv when opening a new terminal. 

Windows: 

```shell
.venv\Scripts\activate
```

Mac/Linux:

```shell
source .venv/bin/activate
```

```
### **Ensure Dataset is in the correct location, Dataset should be in `data/Spotify_Dataset.csv` if missing move it:***
```
mkdir -p data # Create a directory if needed
mv /path/to/Spotify_Dataset.csv data/
```

## Start Zookeeper Service (Terminal 1)

In a terminal (WSL/Mac/Linux):

1. Navigate to the Kafka directory.
2. Ensure we have execute permissions (may not be necessary)
3. Start Zookeeper service. 

```zsh
cd ~/kafka
chmod +x bin/zookeeper-server-start.sh
bin/zookeeper-server-start.sh config/zookeeper.properties
```

Keep this terminal open while working on Kafka.

## Start Kafka (Terminal 2)

Open a NEW terminal. If Windows, open PowerShell and run `wsl` to get a WSL terminal first.

1. Navigate to the Kafka directory.
2. Ensure we have execute permissions (may not be necessary)
3. Start Kafka service. 

```zsh
cd ~/kafka
chmod +x binkafka-server-start.sh
bin/kafka-server-start.sh config/server.properties
```

If you do not have Kafka, then follow this process:
https://github.com/denisecase/buzzline-02-case/blob/main/docs/SETUP-KAFKA.md


## Start a Kafka Producer

Producers generate streaming data for our topics.

In VS Code, open a terminal.
Use the commands below to activate .venv, and start the producer. 

Windows:
```shell
.venv\Scripts\activate
py -m producers.spotify_producer
```

Mac/Linux:
```zsh
source .venv/bin/activate
python3 -m producers.spotify_producer
```

## Start a Kafka Consumer

Consumers process data from topics or logs in real time.

In VS Code, open a NEW terminal in your root project folder. 
Use the commands below to activate .venv, and start the consumer. 

Windows:
```shell
.venv\Scripts\activate
py -m consumers.spotify_consumer_case
```

Mac/Linux:
```zsh
source .venv/bin/activate
python3 -m consumers.spotify_consumer_case
```

## **Start the dashboards**
```
streamlit run dashboard.py
```

## **Run Sentiment Analysis Dashboard**
```
streamlit run sentiment_dashboard.py
```

## **Save and Push it to GitHub!**
```
git add README.md
git commit -m "Updated README"
git push origin main
```

![Alt text for image](https://github.com/Queensdelight/Spotify_streaming_analysis/blob/main/images/visualization.png)

![Alt text for image](https://github.com/Queensdelight/Spotify_streaming_analysis/blob/main/images/streaming%20dashboard.png)

![Alt text for image](https://github.com/Queensdelight/Spotify_streaming_analysis/blob/main/images/sentiment%20score%20by%20genre.jpg)

## Reference
## https://www.linkedin.com/in/david-rodriguez-mayorquin-94808117/
