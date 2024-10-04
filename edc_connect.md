# Interacting with Informatica EDC API using Python

This guide demonstrates how to use Python to interact with Informatica Enterprise Data Catalog (EDC) REST API to create an object with metadata.

## Prerequisites

- Python 3.x
- `requests` library (install using `pip install requests`)

## Python Script

Here's a Python script that shows how to create a custom object in Informatica EDC using its REST API:

```python
import requests
import json

# EDC API base URL
BASE_URL = "https://your-edc-instance.com/access/2/catalog"

# Your API credentials
API_KEY = "your_api_key_here"

# Headers for authentication and content type
headers = {
    "Content-Type": "application/json",
    "INFA-SESSION-ID": API_KEY
}

# Function to create a custom object with metadata
def create_custom_object(name, description, object_type):
    endpoint = f"{BASE_URL}/objects"
    
    payload = {
        "core": {
            "name": name,
            "description": description
        },
        "customAttributes": {
            "objectType": object_type
        }
    }
    
    response = requests.post(endpoint, headers=headers, data=json.dumps(payload))
    
    if response.status_code == 201:
        print(f"Object '{name}' created successfully.")
        return response.json()
    else:
        print(f"Failed to create object. Status code: {response.status_code}")
        print(f"Response: {response.text}")
        return None

# Example usage
if __name__ == "__main__":
    object_name = "Sample Dataset"
    object_description = "This is a sample dataset created via API"
    object_type = "Dataset"
    
    result = create_custom_object(object_name, object_description, object_type)
    
    if result:
        print("Created object details:")
        print(json.dumps(result, indent=2))
```

## Explanation

1. The script imports necessary libraries: `requests` for making HTTP requests and `json` for handling JSON data.

2. It defines the base URL for the EDC API and sets up the headers, including the API key for authentication.

3. The `create_custom_object` function takes parameters for the object's name, description, and type. It then constructs the appropriate payload and sends a POST request to the EDC API.

4. If the object is created successfully (status code 201), it prints a success message and returns the response data. Otherwise, it prints an error message.

5. In the main block, we provide example usage of the function.

## Usage Instructions

To use this script:

1. Replace `"https://your-edc-instance.com/access/2/catalog"` with your actual EDC instance URL.
2. Replace `"your_api_key_here"` with your actual API key.
3. Modify the `object_name`, `object_description`, and `object_type` variables as needed.

## Note

This is a basic example and may need to be adjusted based on your specific EDC version and configuration. Also, error handling and security measures (like secure storage of API keys) should be improved for production use.
