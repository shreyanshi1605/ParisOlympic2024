# Paris Olympic 2024

🚀 Visualizing Victory: Exploring Paris 2024 Olympic Trends with Power BI & Python! 🏅📊

In this project I have used Power BI and Python to analyze athlete performance, medal distribution, and country rankings, pulling in live data from 206 𝐜𝐨𝐮𝐧𝐭𝐫𝐢𝐞𝐬, 11,110 𝐚𝐭𝐡𝐥𝐞𝐭𝐞𝐬 and 1,698 𝐭𝐞𝐚𝐦𝐬. The result? A dynamic, interactive dashboard that captures the excitement and achievements of the Games in real time!

### Project Highlight:

📊Connected live Olympic data using Python to ensure 𝐫𝐞𝐚𝐥-𝐭𝐢𝐦𝐞 𝐮𝐩𝐝𝐚𝐭𝐞𝐬 and reduce manual processes.
🏅Visualized 𝐦𝐞𝐝𝐚𝐥 𝐝𝐢𝐬𝐭𝐫𝐢𝐛𝐮𝐭𝐢𝐨𝐧 by country, gender, and type (Gold, Silver, Bronze).
🔍Integrated dynamic visuals with animated filters for sports categories and country selections.
📉 Historical data analysis from 1896 𝐭𝐨 2022 allows for a deep dive into trends and performance over time.

### Project Workflow:

1. Create an API token on Kaggle
2. Save the API token
3. Python Environment setup
4. Downloading data using Python script
```
import kaggle
import os
import pandas as pd

# Set Kaggle API credentials directory
os.environ['KAGGLE_CONFIG_DIR'] = 'C:/Users/SHREYANSHI SHAH/.kaggle'  

# Specify the dataset identifier
dataset = 'piterfm/paris-2024-olympic-summer-games'

# Set the download path
download_path = 'C:/Users/SHREYANSHI SHAH/Downloads/Olympic/Source'

# Remove existing files in the folder to prevent duplicates or outdated files
for file in os.listdir(download_path):
    file_path = os.path.join(download_path, file)
    try:
        if os.path.isfile(file_path):
            os.unlink(file_path)  # Delete the file
            print(f"Deleted {file_path}")
    except Exception as e:
        print(f"Error deleting {file_path}: {e}")

# Download the dataset using the Kaggle API and unzip the files
kaggle.api.dataset_download_files(dataset, path=download_path, unzip=True)

# List of CSV files to be imported
csv_files = [
    'athletes.csv',
    'events.csv',
    'medallists.csv',
    'medals.csv',
    'medals_total.csv',
    'schedules.csv',
    'schedules_preliminary.csv',
    'teams.csv',
    'torch_route.csv',
    'venues.csv'
]

# Initialize a dictionary to hold DataFrames
dataframes = {}

# Iterate through each CSV file and load it into a DataFrame
for file in csv_files:
    # Construct the full path to the CSV file
    file_path = os.path.join(download_path, file)
    
    # Load the CSV file into a Pandas DataFrame
    df = pd.read_csv(file_path)
    
    # Add the DataFrame to the dictionary using the file name as the key
    table_name = file.split('.')[0]  # Remove the .csv extension
    dataframes[table_name] = df
```
5. Load data in Power BI using Python script
```
# Import necessary libraries
import pandas as pd
import os

# Define the path to the downloaded CSV files
download_path = 'C:/Users/faisa/Downloads/Power BI_Imp Summary/Olympic/Source'

# Load the data into DataFrames
athletes = pd.read_csv(os.path.join(download_path, 'athletes.csv'))
events = pd.read_csv(os.path.join(download_path, 'events.csv'))
medallists = pd.read_csv(os.path.join(download_path, 'medallists.csv'))
medals = pd.read_csv(os.path.join(download_path, 'medals.csv'))
medals_total = pd.read_csv(os.path.join(download_path, 'medals_total.csv'))
schedules = pd.read_csv(os.path.join(download_path, 'schedules.csv'))
schedules_preliminary = pd.read_csv(os.path.join(download_path, 'schedules_preliminary.csv'))
teams = pd.read_csv(os.path.join(download_path, 'teams.csv'))
torch_route = pd.read_csv(os.path.join(download_path, 'torch_route.csv'))
venues = pd.read_csv(os.path.join(download_path, 'venues.csv'))
```
6. Creating visualization in Power BI
![image](https://github.com/user-attachments/assets/2b240043-b55a-44c6-bee9-425363e8591f)
![image](https://github.com/user-attachments/assets/9dad6490-b2c5-4162-82aa-178f168ecaa3)
![image](https://github.com/user-attachments/assets/e4e37350-4dd8-45e1-a33e-133dd690885d)
![image](https://github.com/user-attachments/assets/9b4b37da-b1e2-493d-aa76-5eac7f34f2ec)
![image](https://github.com/user-attachments/assets/e2941d9e-430b-415a-af18-7d50c07ba91c)

### Key Takeways:
- The USA led with the highest number of medals, with 329 𝐆𝐨𝐥𝐝, 333 𝐒𝐢𝐥𝐯𝐞𝐫, 𝐚𝐧𝐝 389 𝐁𝐫𝐨𝐧𝐳𝐞.
- 𝐆𝐞𝐧𝐝𝐞𝐫 𝐛𝐚𝐥𝐚𝐧𝐜𝐞 in medal wins showed impressive performance across male and female athletes.
- Real-time data integration enhanced the analysis experience, allowing dynamic updates as new results emerged.

### Conclusion: 
👨‍💻 This project was a great way to improve my skills in 𝐏𝐲𝐭𝐡𝐨𝐧 𝐬𝐜𝐫𝐢𝐩𝐭𝐢𝐧𝐠 and 𝐏𝐨𝐰𝐞𝐫 𝐁𝐈, combining the power of data integration with interactive visual storytelling.

🔗 Check out the full report and interactive dashboard here: [Dashboard](https://shorturl.at/hRLQv)
