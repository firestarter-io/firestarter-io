# Firestarter.io

Firestarter is a web-based wildfire prediction application.  It is a full stack application, written in typescript.  This readme gives a general overfiew of firestarter's architecture and philosophy.

## Purpose

Wilfire poses a thread to a variety of stakeholders, and is of special interest to those with stakes in urban-wildland boundary areas. Wildfire prediction algorithms strive to apply an analytic framework to a choatic and unpredictable natural phenomenon.  With a core set of location-based data (topography, groundcover, weather, etc), simple physical principles can extrapolated and iterated to predict how fires may behave, helping those who are affected by fire risk to mitigate that risk.

## Philosophy

### Accessibility

Wildfire prediction algorithms require an immense amount of data.  Many wildfire prediction software suites require that data to be readily available in specific formats, which is not user friendly for the average, non-scientist stakeholder.  Many laymen application users require ease of use and accessibility.  The goal of firestarter is to provide a user interface that is engaging to users from various non-scientific backgrounds, while still maintaining scientific and predictive integrity.  To that end, fire-prediction as an engaging and fun web-based application does not yet exist.  The model must also be functional in as wide a geographic area as possible - meaning wherever the required data exists - without placing the burden of data collection, processing, and preparation on the user.  Firestarter.io aims to make wildfire prediction available everywhere, globally.  While this is a large aspiration, it is already possible in places where internet-based GIS data is available (for example in the US or Australia).

### Gamifying

In order to make wildfire prediction more interesting, the user must be able to watch it happen as it progresses on the timescale that they choose (hours, days, weeks).

## Architecture

##
