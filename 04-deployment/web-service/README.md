## Deploying a model as a web-service

* Creating a virtual environment with Pipenv
* Creating a script for predictiong 
* Putting the script into a Flask app
* Packaging the app to Docker


```bash
docker build -t ride-duration-prediction-service:v1 . # build a image using dockerfile
```

```bash 
# -it means in interactive mode so that we can exit using ctrl+C
# --rm means remove image after done
# -p means find the port
docker run -it --rm -p 9696:9696 ride-duration-prediction-service:v1 # run app packaged on docker on the image
```
