# Welcome to your Expo app 👋

Hello! Welcome to our Senior Design Project for SD May 2025. This is an expo application, and the following contents of this read me will walk you through running the application.
Additionally, you may want to refer to our website where you can find a link to the teams Notion page. This page served as the main piece of documentation for our project and holds all info regarding the project itself.

# Get Started


#Install Dependencies
Within the frontend of the application (IowaAdventureCyclistCourseCreator directory) you should run the following command via a terminal
npm install --legacy-peer-deps
If you have issues with this install (errors that are fail this from building) you may run in to having to install certain packages individually and add on --legacy-peer-deps for success


# On the server
View in the notion page https://www.notion.so/Server-Information-13519e0800c280efa7aec7665f4b0181


# Within the backend
cd Backend → npx tsc → cd dist\src\ → node .\index.js
node ./index.js if on mac ^


# Run the frontend
npm start
Download expo go on your phone, scan the qr code, and you should be good to go!



# Restarting from scratch on the server?

Well this sucks.. First step is to set up a sql server! You will adjust the .env in the backend to have the correct IP and login info for the sql server.
Create tables
https://www.notion.so/Database-Table-Scripts-15119e0800c2805092ecc4f502dcd95a

Run the following scripts on the server (find in the scripts folder in the frontend) in this order to get all OSM data for AMES. To change to other cities, change the location in the first python script to be a different city name.
https://www.notion.so/Entering-data-into-database-for-OSM_Data-1cf19e0800c280899ffff370a5493a6d

Log onto the server

nano trial_insert_osm.py

PLACE_NAME = “NEW CITY, Iowa, USA”
ctrl s, ctrl x
Run using python3 trial_insert_osm.py in terminal


Run infer_surfaces_to_sql
Run infer_traffic_to_sql
run infer_difficulty_opentopo (this runs in a batch, so run it over and over until it no longer has segments to add)
Run enrich_altitude_opentopo.py (this runs in a batch as well)
