# Meteo-Bridge-Node-Red
Collection of Node-Red flow for uplod your meteo data to various websites

<img width="1254" alt="Flow" src="https://github.com/user-attachments/assets/6ee64c13-7d97-4878-9fa0-1062a6db093f" />

# What is this flow?
I wanted to upload weather data from my personal weather station, but the solutions found online require paid software.
For this reason I decided to build the function nodes needed to upload weather data to different sites.
Nothing prevents you from modifying or integrating the proposed nodes to adapt them to your needs.
Anyone who wants to contribute is welcome.

# How to...
The 4 nodes dedicated to weather services must be edited.
For each node it will be necessary to configure the various identification data of the weather devices registered on the relative site and the relative API Key.

Regarding the variables, in my case I have the weather variables available as global variables.
Nothing prevents you from modifying the nodes with the variables at your disposal.

# Editor's note:
After careful evaluation, I thought it appropriate to insert an Inject node configured with start after 20 seconds upstream of the flow to ensure that all the variables are available and updated.
Afterwards, the Inject node activates the function nodes every 5 minutes.
In this way, the data will be posted on the various sites with this frequency.
I chose this modus operandi because most sites suggest not using update frequencies greater than 5 minutes to avoid needlessly overloading the servers.
Most of the sites I know have solved this by acquiring a reading every 5 minutes and discarding all the intermediate ones.
Some sites, a few, maybe the simplest ones, warn you that your upload is too frequent.
A few very select ones kick you out and blacklist your station as a "disturber".

This is why I suggest uploading every 5 minutes or more, but not more frequently.
