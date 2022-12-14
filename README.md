# Progress Web Apps

Apps that are capable of behaving like Native Mobile apps but still can be coded with web technologies

## Core Building Blocks

1. Service workers
2. Offline caching
3. Push notifications
4. Background sync
5. Application manifest
6. Responsive design
7. Native device features -> Camera, Geolocation APIs etc

## Progressive Enhancement

# Stages

## Starting



## Application manifest

1. Create manifest.json in the public folder
2. Add few properties

```
{
    "name":"VdApp",
    "short_name":"Vdp",
    "start_url":"/index.html",
    "scope":".",
    "display":"standalone",
    "background_color":"white",
    "description":"the first PWDApp",
    "dir":"ltr",
    "lang":"en-US",
    "orientation":"portrait-primary",
    "icons":[
        {
            "src":"./src/images/icons/app-icon-48x48.png",
            "type":"images/png",
            "sizes":"48x48"
        }

    ]

}

```
> name is for the main name of the app

> short_name is for the short name

> start_url is for the first page to show when the app starts

> scope is for showing pages in PWA

> display is for showing the app as PWA. We can also choose to show the app in different formats
 
> background_color is for the background color when the app starts loading
 
> description is for the description of the app
 
> dir is direction for the app. ltr is leftto right which is default for most countries
 
> lang is for the language

> orientation is for the orientation of the app
 
> icons is for the main icon of the app


3. Add the file path to the html file using ``` <link rel="manifest"   href="/manifest.json"> ```
4. Add 

``` 
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black">
  <meta name="apple-mobile-web-app-title" content="VDapp">
  <link rel="apple-touch-icon" href="./src/images/icons/app-icon-144x144.png" sizes="144x144">
  <meta name="msapplication-TileImage" content="./src/images/icons/app-icon-144x144.png">
  <meta name="msapplication-TileColor" content="white">
  <meta name="theme-color" content="blue">
 ``` 
 for apple devices compatability

5. Add this links to all the html files 

## Service workers

1. Allows to have many native app features
2. Allows to have offline features

Steps

* Registering
1. Go to public folder and create sw.js
2. Go to a js file and enter
```
if('serviceWorker' in navigator){
    navigator.serviceWorker.register('/sw.js',{})
    .then(()=>{
        console.log('Registered')
    });
}else{
    console.log('Service worker not found');
}

```

3. check in application to cross check for service workers instllation


* Reacting to events

1. Add this code to the js file
```
if('serviceWorker' in navigator){
    navigator.serviceWorker.register('/sw.js',{scope:'/help/'})
    .then(()=>{
        console.log('Registered')
    });
}else{
    console.log('Service worker not found');
}

```
2. Add this to the service worker file --> sw.js
```

self.addEventListener('install',function(event){
    console.log('Service worker Installing',event);
})

self.addEventListener('activate',function(event){
    console.log('Service worker Activating',event);
    return self.clients.claim();
})

```

* Non-lifecyle events

1. add the below code in sw.js to check for the event
```

// Non-lifecycle events
self.addEventListener('fetch',function(event){
    console.log('[Service worker] Fetching',event);
});
// for responding with customised fetch rqeuests
    event.respondWith(fetch(event.request));

```



## Promises and Fetch API

## Service worker caching

## Advanced caching strategies

## Caching Dynamic Data with indexedDB

## Responsive Design

## Background sync

## Web push notifications

## Native device features

## Automated Service worker management
