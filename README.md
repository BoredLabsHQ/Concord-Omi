# Concord Channel Finder

**Concord Channel Finder** is an app for Omi that helps users find relevant Concord channels based on the topics extracted from conversations. Using BERT embeddings, it connects conversations with similar channels, allowing users to easily discover communities with shared topics of interest.

## Installation

1. **Download** the Concord Channel Finder app from the Omi app marketplace.
2. **Upload** the app's configuration file (`omi.json`) to Omi if it's not automatically configured by the marketplace.

## Setup

### Prerequisites

- **Concord API Access**: Ensure you have access to Concord's platform and API endpoints.
- **Server URL Configuration**: The app requires a server URL to send requests to. This can be configured through an environment variable.

### Step-by-Step Setup

1. **Configure the Server URL**:
    - Set the `SERVER_URL` environment variable on the server where the app is running. This URL will be used as the base URL for all endpoints.

   ```bash
   export SERVER_URL="https://your-custom-server.com"
   ```

    - This setup will automatically point to:
        - `https://your-custom-server.com/process-memory` for the memory processing webhook.
        - `https://your-custom-server.com/setup-complete` for setup completion verification.

2. **Place Required Files in the Repository Root**:
    - Ensure that `concord-logo.jpg` and `README.md` are located at the root of your repository where the configuration file is stored.

3. **Enable Memory Read Permissions**:
    - The app requires `read_memory` permissions to access conversation data in Omi and provide channel recommendations. You do not need to enable `write_memory` as this app only reads and processes data.

4. **Complete Initial Setup**:
    - Visit [Setup Completion URL](https://your-custom-server.com/setup-complete) (replacing with your configured `SERVER_URL`) to complete the setup configuration.

## Using the Concord Channel Finder

1. **Create Conversations**: Use Omi as usual to create conversation memories.
2. **Process Memory Data**: When a new memory is created, the Concord Channel Finder app will automatically trigger and process the data to find related channels on Concord.
3. **View Recommendations**: Concord Channel Finder will display relevant channels within Omi’s Insights or Recommendations section, helping users connect to channels with similar topics.

## Troubleshooting

- **Server URL Issues**: If Omi cannot reach your server, verify that `SERVER_URL` is correctly set and accessible.
- **Memory Access Issues**: Ensure `read_memory` permissions are enabled for the app to access conversation data.
- **Documentation**: See the full documentation at `/README.md`.

## Support

For any issues or questions, please contact the Concord Team at support@concord-platform.com.