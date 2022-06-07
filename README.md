# SteamCMD in Docker optimized for Unraid
This Docker will download and install SteamCMD and the according game that is pulled via specifying the Tag.

**Please see the different Tags/Branches which games are available.**

## Example Env params for Remnants
| Name | Value | Example |
| --- | --- | --- |
| STEAMCMD_DIR | Folder for SteamCMD | /serverdata/steamcmd |
| SERVER_DIR | Folder for gamefile | /serverdata/serverfiles |
| GAME_ID | The GAME_ID that the container downloads at startup. If you want to install a static or beta version of the game change the value to: '232330 -beta YOURBRANCH' (without quotes, replace YOURBRANCH with the branch or version you want to install). | 1141420 |
| GAME_NAME | SRCDS gamename | remnants |
| GAME_PARAMS | Values to start the server | |
| UID | User Identifier | 99 |
| GID | Group Identifier | 100 |
| GAME_PORT | Port the server will be running on | 7777 |
| VALIDATE | Validates the game data | blank |
| USERNAME | Leave blank for anonymous login | blank |
| PASSWRD | Leave blank for anonymous login | blank |

## Run example for Remnants
```
docker run --name Remnants -d \
	-p 27015:27015 -p 27015:27015/udp \
	--env 'GAME_ID=1141420' \
	--env 'GAME_NAME=remnants' \
	--env 'GAME_PORT=7777' \
	--env 'GAME_PARAMS=' \
	--env 'UID=99' \
	--env 'GID=100' \
	--volume /path/to/steamcmd:/serverdata/steamcmd \
	--volume /path/to/remnants:/serverdata/serverfiles \
	ich777/steamcmd:latest
```

This Docker was mainly edited for better use with Unraid, if you don't use Unraid you should definitely try it!

This Docker is forked from mattieserver, thank you for this wonderfull Docker.

#### Support Thread: https://forums.unraid.net/topic/79530-support-ich777-gameserver-dockers/
