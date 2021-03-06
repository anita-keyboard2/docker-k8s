Docker and Kubernetes Hands On Workshop for the beginners
--------------------------------------------------------
About the project

This project includes sample Python Flask applications and
instructions for installing Docker on your local environment.

The Workshop will be presented in a virtual settings. 
We will have the exact setup on our system (MacOS Catalina).

It is advisable but not a mandatory requirement that you have performed 
these steps beforehand. That way, you can follow along during the workshop
to launch your Docker Container locally and later to a public cloud.
(Google Cloud Platform free tier account).
--------------------------------------------------------
Built With

Python
Flask
docker-engine

--------------------------------------------------------
Installation

1. Clone the repo:
git clone git@github.com:coder-lgtm/docker-k8s.git

2. Make sure you have homebrew available. If not, run following 
 script from the repo:
 ./tools/brew_installtion.sh

3. Python Installation

3.1 Make sure you have python installed
python -version
If not installed run
brew install python

4. To launch the python web application locally, you will need 
some dependencies such as Flask and Requests. Make sure that you 
have pip available.

sudo easy_install pip

pip install flask

pip install requests


5 Launch your  Web Application!

At this point you are ready to run your Python web app locally! 
In the repo
5.1 Run Simple Hello World Web App 
python ./app/hello_world.py 
If you go to the browser and go to http://localhost:5000/,
Check the response to see "Hello World!" greeting

5.2 Run Weather API Web App
python ./app/weather_cock.py
If you go to the browser to see weather data for a Zip Code
http://localhost:5000/weather?zip=94065
Check the response to see weather details as below
{
  "current": {
    "gust_kph": 11.5, 
    "last_updated": "2020-09-06 12:00", 
    "vis_miles": 9.0, 
    "pressure_in": 30.4, 
    "cloud": 0, 
    "precip_mm": 0.0, 
    "is_day": 1, 
    "feelslike_c": 30.0, 
    "condition": {
      "text": "Sunny", 
      "code": 1000, 
      "icon": "//cdn.weatherapi.com/weather/64x64/day/113.png"
    }, 
    "feelslike_f": 85.9, 
    "wind_mph": 0.0, 
    "temp_f": 87.8, 
    "temp_c": 31.0, 
    "last_updated_epoch": 1599418805, 
    "pressure_mb": 1015.0, 
    "vis_km": 16.0, 
    "precip_in": 0.0, 
    "wind_dir": "N", 
    "wind_kph": 0.0, 
    "uv": 8.0, 
    "humidity": 46, 
    "gust_mph": 7.2, 
    "wind_degree": 0
  }, 
  "location": {
    "name": "Redwood City", 
    "country": "USA", 
    "region": "California", 
    "tz_id": "America/Los_Angeles", 
    "lon": -122.25, 
    "lat": 37.53, 
    "localtime_epoch": 1599419443, 
    "localtime": "2020-09-06 12:10"
  }
}

6. Install Docker and Virtualbox

brew update

brew install docker

brew install docker-machine

brew cask install virtualbox

6.1. Validate Docker Installation:

6.1.1 Launch "default" docker machine
docker-machine create --driver virtualbox default

6.1.2. Confirm that the docker machine is running
docker-machine ls 

6.1.3. Connect to Docker 
docker-machine start (if there's no running machine)
docker-machine env
eval $(docker-machine env)

6.1.4. Check if there are any running processes:
 (There will be none and we will launch one during the Workshop!)
docker ps
Expected output is as below:
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

