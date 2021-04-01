<p align="center">
  <img src="./flame.png" width="100"/>
  <h1 align="center">Firestarter.io</h1>
</div>

Firestarter is a web-based wildfire prediction application.  It is a full stack application, written in typescript.  This readme gives a general overview of firestarter's architecture and philosophy.

## Purpose

Wildfire poses a threat to a variety of stakeholders, and is of special interest to those with stakes in urban-wildland boundary areas. Wildfire prediction algorithms strive to apply an analytic framework to a choatic and unpredictable natural phenomenon.  With a core set of location-based data (topography, groundcover, weather, etc), simple physical principles can extrapolated and iterated to predict how fires may behave.  Such predictions can help mitigate the risk of wildfires in fire-prone areas.

## Philosophy

### 🌐 Accessibility

Wildfire prediction algorithms require an immense amount of data.  Many wildfire prediction software suites require that data to be pre-downloaded in specific formats, which is not user friendly for the average, non-scientist stakeholder.  Ordinary application users require ease of use and accessibility.  The goal of firestarter is to provide a user interface that is engaging to users from various non-scientific backgrounds, while still maintaining scientific and predictive integrity.  To that end, fire-prediction as an engaging and fun web-based application does not yet exist.  

The model must also be functional in as wide a geographic area as possible - meaning wherever the required data exists - without placing the burden of data collection, processing, and preparation on the user.  Firestarter.io aims to make wildfire prediction available everywhere, globally.  While this is a large aspiration, it is already possible in places where internet-based GIS data required for fire prediction models is available (for example in the US or Australia).

### 👨‍🚒 Stakeholder Concepts

Different types of stakeholders will have very different interests in wildfire prediction.  They may have very different questions to answer or input to give, whether regarding a single fire, fire season, or fire as a force to be dealt with over a long period of time.  Home and property owners might ask, "Is my property at risk?  Will I need to evacuate?  Am I safe from fire?", while firefighters might ask, "What resources will we need to fight this fire / fires in this area?  Will it be 'worth it' to apply these resources, or is it better to let the fire burn?"  Land developers may ask whether or not its worth building property in very fire-proned areas, and insurance companies may ask how the likelihood of fire in an area may affect how they craft their insurance policies for property owners.  Firestarter aims to customize the UI and algorithm parameters to help each type of stakeholder answer the questions that are relevant to *them*.

A short list of stakeholders includes:
- Home / property owners
- Firefighters
- Land developers
- City planners
- Insurance companies
- Environmental scientists

### 🙋‍♀️ Stakeholder Decisions as Algorithm Parameters

When a fire arises, different stakeholders will make decisions in response to the nature of the fire and the surrounding geographic features.  Where will a fire department choose to contain a fire?  Based on that choice, which property owners will choose to evacuate, and which will choose to stay.  How will these choices affect property damage?  How will property damage for a given fire season affect insurance policies written in the following years?  Each person makes decisions that will affect others and they way that wildfire plays a part in their life.

### 🧑‍💻 UI Goals

In order to make wildfire prediction more interesting, the user must be able to watch it happen as it progresses on the timescale that they choose (hours, days, weeks, years).

With different users coming to the App with different questions, one aspiration would be to create different types of *roles* a user can choose (whether on a per-account or per-campaign basis).  Different roles would have different UI experiences, meaning the options and data shown to them would be unique to that role, as would the potential inputs


## 🏛️ Architecture

Firestarter is a full stack web application. The core algorithm lives in a node-typescript application.  The goal with this architecture is to offload the computational burden from the user's machine to the server, which could be architected to run on a compute-optimized machine (through AWS, for instance).  The UI, which may live in a web browser or as a native application, communicates to the server application, providing some basic data about the simulation, or Campaign, that the user wants to run (time, place, length, parameters, etc.).  The algorithm performs the calculations, generating a series of snapshots of the fire model in time, or Timesteps, which are then sent back to the client.  The client may play these back using the UI's play function, or there may be some back and forth and the client provides input based on prompts from the algorithm.

