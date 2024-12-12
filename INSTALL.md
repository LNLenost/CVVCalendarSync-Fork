# CVVCalendarSync Installation Guide

## Prerequisites

- ![Python](https://www.python.org/static/community_logos/python-logo.png) Python 3.6 or higher
- ![Google Cloud](https://cloud.google.com/images/social-icon-google-cloud-1200-630.png) Google account
- ![ClasseViva](https://www.spaggiari.eu/portale/vivifamiglia/images/logo_classeviva.png) Access to ClasseViva account

## Step 1: Clone the Repository

First, clone the repository to your local machine:

```bash
git clone https://github.com/yourusername/CVVCalendarSync.git
cd CVVCalendarSync
```

## Step 2: Set Up Google Calendar API
1. Go to the [Google Cloud Console](https://console.cloud.google.com/).
2. Create a new project:
    - Click on the project dropdown at the top of the page.
    - Click "New Project".
    - Enter the project name and other details, then click "Create".
3. Enable the Google Calendar API for your project:
    - In the Google Cloud Console, go to "APIs & Services" > "Library".
    - Search for "Google Calendar API".
    - Click on "Google Calendar API" and then click "Enable".
4. Create a service account:
    - Go to "IAM & Admin" > "Service Accounts".
    - Click "Create Service Account".
    - Fill in the details and click "Create".
    - Assign the "Editor" role to the service account.
    - Click "Done".
5. Create a JSON key for the service account:
    - Click on the service account you just created.
    - Go to the "Keys" tab.
    - Click "Add Key" > "Create New Key".
    - Select "JSON" and click "Create". Save the JSON file to your project directory.
6. Create a new Google Calendar:
    - Go to Google Calendar.
    - Click on the plus sign next to "Other calendars".
    - Select "Create new calendar".
    - Fill in the calendar name and other details, then click "Create calendar".
7. Share your Google Calendar with the service account:
    - Go to Google Calendar.
    - Click on the three dots next to the calendar you want to share.
    - Click "Settings and sharing".
    - Under "Share with specific people", add the service account email and give it "Make changes to events" permission.

## Step 3: Configure the Script

1. Rename `config.example.json` to `config.json`:

```bash
mv config.example.json config.json
```

2. Edit `config.json` and fill in the required fields:

```json
{
     "user_id": "your_classeviva_user_id",
     "user_pass": "your_classeviva_password",
     "calendar_id": "your_google_calendar_id",
     "credentials_file": "credentials.json" # NOTE: put the file in the same directory and rename it to "credentials.json"
}
```

## Step 4: Install Dependencies

Install the required Python packages:

```bash
pip install -r requirements.txt
```

## Step 5: Run the Script

Run the script to sync your ClasseViva agenda with Google Calendar:

```bash
python CVVCalendarSync.py
```

## Troubleshooting

If you encounter any issues, please check the error messages and ensure that all configurations are correct. You can also refer to the [Google Calendar API documentation](https://developers.google.com/calendar) for more details.
