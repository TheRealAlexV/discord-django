# Reloaded-gg Sync

Author: DeMiNe0([TheRealAlexv](https://github.com/TheRealAlexV))

An app for Syncing Reloaded-gg discord users with different games and services.

# How to use

1. Start by cloning this Repo.

2. Next create a copy of the .env file: `cp .env.example .env`

## Setup Discord for API access and configure your .env file

Discord oauth credentials are needed next.

1. Create Discord account and login with the browser.

2. Go to [Discord Developer portal](https://discord.com/developers/applications) and create your own application, click OAuth2 and copy your client ID and client secret.

  Then paste them into the `.env` file.
  
    client_id = Your client id
    client_secret = Your client secret

3. In the same section of Oauth2, click on Add redirect and enter this address for callback.

  `http://127.0.0.1:8000/auth`

  ## NOTE:
  If you want to run this project on a server or host, put your domain instead of 127.0.0.1:8000 and go to the `settings.py` file in the DiscordOauth2 folder and set `DEBUG` to `False` and put your domain in the ALLOWED_HOSTS list, e.g => `www.mydomain.com` or `mydomain.com`, then change `redirect_uri` to `http://yourdomain/auth`
    
4. Then with the help of OAuth2 URL Generator In Oauth2, by selecting the url you added in Redirects in the SELECT REDIRECT URL section and checking `identify` and `guilds`, the  url generator will give you a url, copy it and paste it in .env file
        
  auth_url_discord = The url you copied

## Running the App
There are several ways that you can run this; either directly via source or via docker.

### Run via Docker

Probably the easiest and quickest way to get up and running.

Use the included docker-compose.yml file to run the app: 
`docker-compose up -d`

### Build and Run from Source

This method is for users who with to have more control over the python code that runs. Great for helping with development.

1. Enter the app directory: `cd ./app`

2. Make a virtenv for this project if you want to follow good coding pracices and make troubleshooting easier. [How to use Python virtualenv](https://pythonbasics.org/virtualenv/)

3. Open command prompt inside the folder where you cloned repo and enter this command `pip install -r requirements.txt`.
          
4. Build the sqlite3 db: `python manage.py migrate` 

5. Run the app: `python manage.py runserver`

## Accessing the App

Visit `http://127.0.0.1:8000/home` if you're running this locally, or the URL of the server if you are running it remotely.
