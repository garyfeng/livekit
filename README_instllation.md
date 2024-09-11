# Installation Instructions
----

The following is based on Windows instllation steps. 

1. Follow https://github.com/livekit/livekit-cli/tree/v2.1.0 to install LiveKit CLI, aka `lk`. Note that some older docs reference to `livekit_cli`; it looks like it now becomes `lk` instead. Follow the link above to download the windows version in a zip. Unzip and get the `lk.exe` file. I moved it to the `livekit` repo

2. Do `lk cloud auth` to add the default cloud project. It asks the name of your local project, which I entered "home windows testing". It then launches the browser and connects to the livekit.io default project, which is https://cloud.livekit.io/projects/p_4nap2lbjdr0/aggstats (the dashboard site). After this step, it returns to the cli and asks if you want to add this cloud project as the default, to which I said yes. It then shows the API key associated with this project. 

In my case the API keys and tokens can be generated using the livekit.io project page, https://cloud.livekit.io/projects/p_4nap2lbjdr0/settings/keys . Also see https://docs.livekit.io/home/cloud/keys-and-tokens/#Generating-access-tokens

3. Get `livekit-server.exe`, from https://github.com/livekit/livekit/releases/tag/v1.7.2. Download the appropriate precomputed zip file. Unzip and get the `livekit-server.exe`, which you can copy to the project directory, along with `lk.exe`

Launch it with `live-kit-server --dev`, and hit http://localhsot:7880, you should get an "ok" as response. 

4. To connect to a demo project on the cloud, 
  1. go to https://cloud.livekit.io/projects/p_4nap2lbjdr0/settings/keys, find the right key and click on the "..." to generate token. You need to put in your username and the chat room name to generate the key, which has a set expiration date (default to 900 hours). Then you get the token to copy. 
  2. go to the demo site https://meet.livekit.io/?tab=custom, enter your livekit socket url starting with `wss://...` and the token generated above. Enter the chat room (it would be only you if everything goes right; you can chat, but notbody will respond)


----
# Installing for running livekit agent


```
python -m venv venv   
venv\Scripts\activate    # this line gives error but it did active the `venv` virtual environment
# optional to update pip
# python.exe -m pip install --upgrade pip
# the following line failed once, but rerunning worked
pip install livekit livekit-agents livekit-plugins-deepgram livekit-plugins-openai livekit-plugins-silero
```
