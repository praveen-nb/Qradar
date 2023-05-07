import requests
import json

# Define the API endpoint and API token
api_endpoint = "https://your.qradar.instance/api/"
api_token = "your_api_token"

# Define the headers for the API request
headers = {
    "Content-Type": "application/json",
    "SEC": api_token
}

# Define the payload for the API request
payload = {
    "name": "My New Log Source",
    "description": "This is a new log source.",
    "logSourceCategory": "Syslog",
    "protocol": "UDP",
    "port": 514,
    "hostname": "logsource.example.com"
}

# Create the log source
logsource_url = api_endpoint + "config/event_sources/log_sources"
response = requests.post(logsource_url, headers=headers, json=payload, verify=False)

# Print the response
print(response.json())
