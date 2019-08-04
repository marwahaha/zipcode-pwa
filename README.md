# Vue Zipcode PWA

## Project planning and how it works

It uses a package named Ionic/vue which allows us to use Ionic for the components within our Vue App so we can have this cool mobile look.

For the funnctionality well basicly we can look up information for a zipcode so if we type in 94203 and click find, is going to give us the city, the state, the abbreviation, the latitude and the longitude. After that we can clear the information shown to us to make another request.

The way this functionality can achive this is through a third party API called Zipopotam. It also going to have some error checking with the Ionic modal/alert.

After build it up, is going to be deploy into firebase, and then progressive web app functionality will be implementet. How this is done is by creating a service worker that will cache all the assets and then cache every request that gets back. So any data we get from any request should get cached for online viewing.

To give an example inside the app devtools and we see the app have a manifest and a serivce worker. Then bellow that information is everything that is being cache, which is all the assets and every request that we get. So those are the zipcodes that are already done.

Basicly all this stuff will work offline because all the data has been cached. If we go to network and go offline, this will mimic not having and internet connection, so after reload you will see the app still working because the app have all the assets. So if we try in offline it wokrs.

## Project setup

```
vue create zipcode-pwa
```

```
npm i @ionic/vue
```
