---
layout: project
title:  "CTA Bus Tracking App"
date:   2014-06-03 18:54:01
categories: Sinatra
---
[![Build Status](https://travis-ci.org/rdalin82/CTABusApp.svg?branch=master)](https://travis-ci.org/rdalin82/CTABusApp)


## Summary 
This is an app created with the Programming language Ruby, the DSL microframework Sinatra, Bootstrap frontend framework, XML parsing gem Nokogiri, and the Geo-Distance gem for calculating the distance between two GPS coordinates. Information used to support this app is from the CTA Bus Tracking API which provides real time information regarding buses through out the CTA system.

The app requests from CTA the location of buses from each route and filters them based on which destination they are heading to. Then it calculates the distance between each bus and the one before and after it. The distance is applied to the "clumping" matrix displayed below and is based on the closest distance between all the buses. Currently I have only put in a few sample routes, but plan on adding more.

## Challenges
+ Calculating Distances on a non-flat surface (ie Earth) 
  - Used Geo-Distances gem's haversine formula
+ Converting and parsing CTA XML data
+ Refreshing data from the server by polling server
+ Submitted issue to Geo-Distance gem regarding a dependency gem that required ActiveRecord which caused the library to not work on Sinatra. Found work around by including ActiveRecord into project to prevent crashing.  

Missing ActiveRecord code from the dependency: 
   
    def extract_options!
      if last.is_a?(Hash) && last.extractable_options?
        pop
      else
        {}
      end
    end 

## Technologies Used 
+ Ruby
+ Nokogiri
+ Sinatra
+ Bootstrap
+ Geo-Distances (used for calculating distance between buses)
+ CTA API 
+ Google Maps API

Javascript code that allows refreshing: 


      // getting initial data 
     var vehicles = {
        ids: <%= @route.vehicles %>, 
        lats: <%= @route.lat %>,
        lons: <%= @route.lon %> 
      }  
      for (var i = 0; i < vehicles.ids.length; i++) {
        var marker = new google.maps.Marker({
          position: { lat: vehicles.lats[i], lng: vehicles.lons[i] },
          map: map, 
          title: "bus"+vehicles.ids[i].toString(),
          icon: '/bus.png'
        });
        markers.push(marker);
      }
      // drawing buses on the map
      function drawOnMap(){
        var routeInfo = {
        route: <%= @route.route.to_json %>, 
        destination: <%= @route.destination.to_json %>
      }
      // getting new data in JSON
      $.getJSON("/api/"+routeInfo.route+"/"+routeInfo.destination, function(data){
          markers = [];
          for (i in data) {
           console.log(data[i].lat);
            var marker = new google.maps.Marker({
              position: { lat: data[i].lat, lng: data[i].lon }, 
              map: map, 
              title: "bus" + data[i].bus.toString(),
              icon: {
                url: '/bus.png'
              }
            });
            markers.push(marker)
          }
        });
      }
      // Clear existing buses so you can draw new ones
      function clearMarkers(){
        for (var i=0; i<markers.length; i++){
          markers[i].setMap(null);
        }
        markers = new Array();
      }
      // setting an interval for refreshing bus locations
      setInterval(function(){
        clearMarkers();
          drawOnMap();
        }, 60000);
    }



The application is located at: [CTA Bus Tracking on Heroku](http://rdalin-cta.herokuapp.com)


The github repo is at: [Github Repo](https://github.com/rdalin82/CTABusApp)

