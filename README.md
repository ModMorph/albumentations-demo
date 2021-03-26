# golly-dalle ad hoc debug/perception lab

To help investigate the behavior of the CLIP and Dall-E VAE packages under different conditions, and find better techniques for employing them for Generative Models & Zero-Shot Classification Learning, I decided to get a better structured streamlit app to combine with my ad hoc experiments using streamlit for comparative analysis of Dall-E and CLIP. So I found the albumentations-demo [https://albumentations-demo.herokuapp.com/](https://albumentations-demo.herokuapp.com/) from Ilia Larchenko, which already had a panopoly of effects I wanted to experiment with comparatively and seemed well structured compared to the spaghetti of my first streamlit apps. 

## TBD
Plan on hosting this on streamlit - at which time will add a URL here.

## License
MIT. OpenAI's CLIP models & Dall-E VAE are under Apache 2.0 Licenses and Modified MIT respectively (last time I checked). 

## Installation and run
```
git clone https://github.com/ModMorph/golly-dalle
cd golly-dalle
git submodule update --init --recursive
pip install -r requirements.txt
streamlit run src/app.py
```


If you want to work with you own images just replace the last line with:
```
streamlit run src/app.py -- --image_folder PATH_TO_YOUR_IMAGE_FOLDER
```

If your images have some unusual proportions you can use `image_width` parameter to set the width in pixels of the original image to show. The width of the transformed image and heights of both images will be computed automatically. Default value of width is `400`.
```
streamlit run src/app.py -- --image_width INT_VALUE_OF_WIDTH
```


In your terminal you will see the link to the running local service similar to : 
```console
  You can now view your Streamlit app in your browser.

  Network URL: http://YOUR_LOCAL_IP:8501
  External URL: http://YOUR_GLOBAL_IP:8501
```
Just follow the local link to use the service.

## Run in docker
You can run the service in docker:
```
docker-compose up
```
It will be available at http://DOCKER_HOST_IP:8501

## How to use

The interface is very simple and intuitive:
1. On the left you have a control sidebar. Select the "Simple" mode. You can choose the image and the transformation.
2. After that you will see the control elements for the every parameter this transformation has.
3. Every time you change any parameter you will see the augmented version of the image on the right side of your screen.
4. Below the images you can find a code for calling of the augmentation with selected parameters.
5. You can also find there the original docstring for this transformation.
![screenshot](docs/screenshot.jpg?raw=true)


## Professional mode
In the professional mode you can:
1. Upload your own image
2. Combine multiple transformations
3. See the random parameters used to get the result

Be aware that in Professional mode some combination of parameters of different transformations can be invalid. You should control it.

## Links
* Albumentations library: [github.com/albumentations-team/albumentations](https://github.com/albumentations-team/albumentations)
* Image Source: [pexels.com/royalty-free-images](https://pexels.com/royalty-free-images/)
* Streamlit - framework powering this app [github.com/streamlit/streamlit](https://github.com/streamlit/streamlit)  
