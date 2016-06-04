---
layout: project
title:  "CTA Bus Tracking App"
date:   2014-06-03 18:54:01
categories: Sinatra
---

This is an app created with the Programming language Ruby, the DSL microframework Sinatra, Bootstrap frontend framework, XML parsing gem Nokogiri, and the Geo-Distance gem for calculating the distance between two GPS coordinates. Information used to support this app is from the CTA Bus Tracking API which provides real time information regarding buses through out the CTA system.

The app requests from CTA the location of buses from each route and filters them based on which destination they are heading to. Then it calculates the distance between each bus and the one before and after it. The distance is applied to the "clumping" matrix displayed below and is based on the closest distance between all the buses. Currently I have only put in a few sample routes, but plan on adding more.

The application is located at: [CTA Bus Tracking on Heroku](http://rdalin-cta.herokuapp.com)


The github repo is at: [Github Repo](https://github.com/rdalin82/CTABusApp)

