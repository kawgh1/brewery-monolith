[![CircleCI](https://circleci.com/gh/sfg-beer-works/brewery-monolith.svg?style=svg)](https://circleci.com/gh/sfg-beer-works/brewery-monolith)
# Brewery UI Monolith

## Troubleshooting

This project was forked from https://github.com/sfg-beer-works/brewery-monolith
and is part of John Thompson's Spring Microservices course

This Monolith application ran out of the box but its LESS/CSS configuration and UI display was all whacked out.
- Took me quite a while to debug.  No one else appears to have gotten the UI to display properly (instead of bare HTML). I shared my steps.
    - Steps are here:
        - https://github.com/kawgh1/brewery-monolith/blob/master/troubleshootingSteps.txt

# Notes

Beer Works Monolith

- Example Spring Framework Project
- A Monolith Application to be deconstructed into Microservices
- https://github.com/sfg-beer-works/brewery-monolith

- ### Beer Works
	- Models as a Brewery
	- The Beer Works Brewery has:
		- Beers
		- Beer Inventory
		- Beer Orders
		- Customers

	- ### Beer Works - Tasting Room
		- Creates 'demand' - Brewery needs to consume beer inventory to supply tasting room orders
		- Demand triggers inventory reduction
		- Inventory reduction will trigger brewing of beer
		- Brewing will create inventory

	- ### Beer Works - Technology
		- Spring Boot / Spring Framework
		- Hibernate / Spring Data JPA
		- Project Lombok / MapStruct
		- Thymeleaf for UI Views
		- Spring Scheduled Tasks
		- Messaging and Sagas
		- Spring Events
		- Spring Cloud
		- Spring MVC