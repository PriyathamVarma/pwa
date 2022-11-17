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

3. Add the file path to the html file

## Service workers

## Promises and Fetch API

## Service worker caching

## Advanced caching strategies

## Caching Dynamic Data with indexedDB

## Responsive Design

## Background sync

## Web push notifications

## Native device features

## Automated Service worker management