# DubMap

**An interactive campus map built for University of Washington students** — find buildings, resources, and specific classrooms by room number, all in one place.

## Motivation

Stanford's TreeMap was an invaluable tool during my time there. UW didn't have an equivalent. DubMap fills that gap — giving Huskies a fast, intuitive way to navigate one of the largest campuses in the US.

## Core Technical Concept: WiFi-Based Indoor Positioning

The core innovation behind DubMap is **WiFi trilateration for indoor navigation**. 

Every UW building is blanketed with WiFi access points. By measuring the signal strength (RSSI) from multiple access points simultaneously, DubMap can triangulate a user's position within a building down to the room level — no GPS required (GPS signals don't penetrate buildings reliably).

The flow works like this:
1. Device scans for nearby WiFi access points and reads their signal strengths
2. Known AP locations on campus act as fixed reference points
3. Signal strength falloff is used to estimate distance from each AP
4. Trilateration across 3+ APs pinpoints the user's location on a floor plan
5. That position is overlaid on the indoor map, guiding the user turn-by-turn to their exact classroom

This is the same underlying concept used by Google Maps and Apple Maps indoors — applied specifically to UW's campus infrastructure.

## Features

- 🗺️ Search for any UW building or campus resource
- 🔢 Look up specific classrooms by room number
- 📍 Outdoor routing across campus via Leaflet Routing Machine
- 🏢 Indoor positioning via WiFi trilateration + Pointr SDK
- 🎨 UW-branded UI (Husky purple)

## Tech Stack

- **Leaflet.js** — lightweight, open-source map rendering
- **MapBox GL JS** — high-quality vector tile rendering
- **Leaflet Routing Machine** — campus navigation and directions
- **Pointr SDK** — indoor floor plans and positioning layer
- **Vanilla HTML/CSS/JS** — no framework overhead, fast load times

## Live Demo

[github.com/ozbot11/DubMap](https://github.com/ozbot11/DubMap)
