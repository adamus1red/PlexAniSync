# Plex to AniList Sync
![Logo](logo.png)

If you manage your Anime with Plex this will allow you to sync your libraries to [AniList](https://anilist.co)  , recommend using Plex with the [HAMA agent](https://github.com/ZeroQI/Hama.bundle) for best Anime name matches.

Unwatched Anime in Plex will not be synced so only those that have at least one watched episode, updates to AniList are only send with changes so need to worry about messing up watch history.


This version is based on my previous project  [PlexMalSync](https://github.com/RickDB/PlexMALSync) which due to MAL closing their API is no longer working, this might change in the future and if it does will resume working on that again as as well.


**Disclaimer: Since this is the first public release bugs may occur so be careful and if you want to test it out first without updating your actual AniList entries check out the ``addtional options`` section from this readme.**

# Setup

## Step 1 - Configuration

From the project directory copy the example settings file `settings.ini.example` to `settings.ini`, open `settings.ini` with your favorite editor and edit where needed.

### Plex
For the Direct IP authentication method you need to find your token manually:

https://support.plex.tv/articles/204059436-finding-an-authentication-token-x-plex-token/


```
[ANILIST]
username = GoblinSlayer
access_token = 1234etc..
```

### AniList
For AniList you need get a so called 'access_token', you can retrieve that here and if not logged in will ask you to do so:

https://anilist.co/api/v2/oauth/authorize?client_id=1549&response_type=token

Make sure copy the entire key as it is pretty long and paste that in the settings file under 'access_token', no need to enclose it just paste it as-is.

Afterwards make sure to also fill in your AniList username as well which is your actual username not your e-mail address.
Example AniList config:

```
[ANILIST]
username = GoblinSlayer
access_token = iLikeToastyGoblins.
```

## Step 2 - Install requirements

Install requirements using this python command in the project folder:

`pip install -r requirements.txt`

## Step 3 - Start syncing

Now that configuration is finished and requirements have been installed we can finally start the sync script:

`python PlexAniSync.py`

Depending on library size and server can take a few minutes to finish.

## Addtional options

In ``PlexAniSync.py`` there's a variable called 'emulate_list_updates' which you can set to True or False, if set to True it will **NOT** update your AniList which is useful if you want to do a test run to check if everything lines up properly.

## Requirements

[Python 3 (tested with 3.6.4)](https://www.python.org/)

## Support

Support thread is located on Plex Forums:

N/A yet

## Planned

Currently planned for future releases:

- [ ] Improve error handling
- [ ] Code cleanup and refactoring

## Credits

[Python-PlexAPI](https://github.com/pkkid/python-plexapi)