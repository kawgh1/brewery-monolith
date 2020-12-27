## Troubleshooting

This Monolith application ran out of the box but its LESS/CSS configuration and UI display was all whacked out.
- Took me quite a while to debug. Steps are here:
- https://github.com/kawgh1/brewery-monolith-troubleshootingSteps.txt




[![CircleCI](https://circleci.com/gh/sfg-beer-works/brewery-monolith.svg?style=svg)](https://circleci.com/gh/sfg-beer-works/brewery-monolith)
# Brewery UI Monolith

This repository contains source code examples used to support my on-line courses about the Spring Framework.

You can learn more about the courses here:
* [Spring Boot Microservices with Spring Cloud](https://www.udemy.com/spring-boot-microservices-with-spring-cloud-beginner-to-guru/?couponCode=GIT_HUB2)
* [Spring Framework 5: Beginner to Guru](https://www.udemy.com/course/spring-framework-5-beginner-to-guru/?couponCode=GITHUB_SFGPETCLINIC)
* [Testing Spring Boot: Beginner to Guru](https://www.udemy.com/testing-spring-boot-beginner-to-guru/?couponCode=GITHUB_REPO_SF5B2G)

# This took a lot of troubleshooting to get the LESS/CSS to display properly
- download these fonts and put in resources/fonts folder 
    - https://github.com/Mobirise/Free-Bootstrap-Template/tree/master/assets/bootstrap/fonts


# Notes

Beer Works Monolith

- Example Spring Framework Project
- A Monolith Application to be deconstructed into Microservices
- https://github.com/sfg-beer-works/brewery-monolith

- ###Beer Works
	- Models as a Brewery
	- The Beer Works Brewery has:
		- Beers
		- Beer Inventory
		- Beer Orders
		- Customers

	- ###Beer Works - Tasting Room
		- Creates 'demand' - Brewery needs to consume beer inventory to supply tasting room orders
		- Demand triggers inventory reduction
		- Inventory reduction will trigger brewing of beer
		- Brewing will create inventory

	- ###Beer Works - Technology
		- Spring Boot / Spring Framework
		- Hibernate / Spring Data JPA
		- Project Lombok / MapStruct
		- Thymeleaf for UI Views
		- Spring Scheduled Tasks
		- Messaging and Sagas
		- Spring Events
		- Spring Cloud
		- Spring MVC