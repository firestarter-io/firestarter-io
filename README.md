# Firestarter.io

Firestarter is a web-based wildfire prediction application.  It is a full stack application, written in typescript.  This readme gives a general overfiew of firestarter's architecture and philosophy.

## Purpose

Wilfire poses a threat to a variety of stakeholders, and is of special interest to those with stakes in urban-wildland boundary areas. Wildfire prediction algorithms strive to apply an analytic framework to a choatic and unpredictable natural phenomenon.  With a core set of location-based data (topography, groundcover, weather, etc), simple physical principles can extrapolated and iterated to predict how fires may behave.  Such predictions can help mitigate the risk of wildfires in fire-prone areas.

## Philosophy

### Accessibility

Wildfire prediction algorithms require an immense amount of data.  Many wildfire prediction software suites require that data to be pre-downloaded in specific formats, which is not user friendly for the average, non-scientist stakeholder.  Ordinary application users require ease of use and accessibility.  The goal of firestarter is to provide a user interface that is engaging to users from various non-scientific backgrounds, while still maintaining scientific and predictive integrity.  To that end, fire-prediction as an engaging and fun web-based application does not yet exist.  The model must also be functional in as wide a geographic area as possible - meaning wherever the required data exists - without placing the burden of data collection, processing, and preparation on the user.  Firestarter.io aims to make wildfire prediction available everywhere, globally.  While this is a large aspiration, it is already possible in places where internet-based GIS data is available (for example in the US or Australia).

### Gamifying

In order to make wildfire prediction more interesting, the user must be able to watch it happen as it progresses on the timescale that they choose (hours, days, weeks).

## Architecture

Firestarter is a full stack web application. The core algorithm lives in a node-typescript application.  The goal with this architecture is to offload the computational burden from the user's machine to the server, which could be architected to run on a compute-optimized machine (through AWS, for instance).  The UI, which may live in a web browser as as a native application, communicates to the server application, providing some basic data about the simulation, or Campaign, that the user wants to run (time, place, length, parameters, etc.).  The algorithm performs the calculations, generating a series of snapshots of the fire model in time, or Timesteps, which are then sent back to the client.  The client may play these back using the UI's play function, or there may be some back and forth and the client provides input based on prompts from the algorithm.

