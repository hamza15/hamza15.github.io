---
layout: post
title:      "Mod1 - IMDB_CLI"
date:       2020-09-18 03:02:56 -0400
permalink:  mod1_-_imdb_cli
---


With Module 1 coming to an end soon our cohort got the opportunity to work on our first project. The project's requirements were pretty straightforward. 

**Build a Ruby gem that provides a Command Line Interface (CLI) to an external data source. The CLI should be composed of an Object Oriented Ruby application. The user should be able to interract with CLI and go one level deep (User can make a choice and then get detailed information about their choice). And finally use all you've learned about Ruby and CLI Applications in Ruby to complete this project.** 


Whether we chose to use an API or Scraping to ingest data into our project and what the classe and instance model would like were left for us to decide. Although daunting at first, I decided to spend a day researching API's and websites that would fit the requirements. I came across IMDB's API, which seemed like a great prospect to setup a project with. 

The first issue that I ran into with the IMDB API was although IMDb does officially have a public API called Search Suggestions, it is undocumented. Further research into said issue led me to find that the API could change at any point since IMDB does not support third party APIs which could potentially break my project at any point. It also seemed that using an API seemed simpler, since most documentation by the provider had examples of GET requests and the resulting output. It seemed like a great opportunity for me to dive deep into Nokogiri and scraping. With the external data source and the ingestion method decided, I began building out my project.

### Experience:

IMDB_CLI allows a user to view, select and watch a trailer for one of the top 15 Horror Movies on IMDB (based on popularity). The CLI starts the interaction by first calling the Scraper class methods which use Nokogiri to get the names and respective release dates of the movies as seen on IMDB. These movies are listed along side an index number which allows the user to select a movie based on the index number. The CLI also calls on a Scraper class method to use Nokogiri and pull attributes like director, start names, reviews and a URL for the movies' trailers. These attributes are stored in hashes which are then stored in an array. The next step is to create Movie objects from these attributes and store them in an .all method which can be accessed later. We ask our user for input and he has three options:
1. Select a movie based on index number.
2. List the movies again.
3. Exit.

**Note: If the user enters an invalid entry, he is shown an error message and asked to re-enter a valid entry.**

#### 1. Select a movie based on index number.

If the user selects a movie based, he is shown attributes of the movie and is asked if he would like to watch the trailer. Entering 'y' would open his default browser and lead him to the URL of the movie's trailer.

#### List the movies again.
If the user inputs "list" the list of movies are listed again.

#### Exit.
If the user types "exit" he is exited out of our program.


