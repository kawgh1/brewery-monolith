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
		
- ### Monolith Deconstruction Strategies

    - ### Domain Driven Design
        - **Domain Driven Design (DDD)** is a methodology to bring clarity to complexity
        - Some call DDD an extension of Object Oriented Programming at a higher level
        - DDD concepts can be used to model complex systems
        - DDD concept is accredited to Eric Evans from his 2003 book
            - "Domain-Driven Design: Tackling Complexity in the Heart of Software"
            - https://github.com/kawgh1/brewery-monolith/blob/master/DDD_Reference_2015-03.pdf
            
        - #### DDD Definitions
            - **Domain** - A sphere of knowledge, influence or activity. The subject area which the user applies a program is the domain of the software.
            - **Model** - A system of abstractions that describes the selected aspects of a domain and can be used to solve problems related to that domain.
            - **Ubiquitous Language** - A language structured around the domain model and used by all team members within a bounded context to connect all activities of the team with the software.
            - **Context** - The setting in which a word or statement appears that determines its meaning. Statements about a model can only be understood in context.
            - **Bounded Context** - A description of a boundary(typically a subsystem, or the work of a particular item) within which a particular model is defined and applicable.
        
        - #### Building Blocks
            - **Entities** - Not a traditional Object. Represent a thread of identity that runs through time and often across distinct representations.
            - **Value Objects** - Some objects describe or compute some characteristic of a thing. Immutable object, with attributes - but with no identity.
            - **Domain Events** - Something happened that the domain experts care about. An object that is used to record a discrete event related to model activity.
            - **Services** - Sometimes it just isn't a thing. Some concepts are not natural to model as objects.
            - **Aggregates** - are a cluster of entities and value objects.
            - **Repositories** - Query access to aggregates express in the ubiquitous language. Like a specialized service.
            - **Factories** - Like OOP, facrtories create aggregates.
        
        - #### DDD for Microservice Design
            - Think in Bounded Contexts-
                - **Bounded Context** - A description of a boundary(typically a subsystem, or the work of a particular item) within which a particular model is defined and applicable.
            - A bounded context will help you contain complexity
            - Contexts define common terminology
            - DDD Bounded Contexts help you with organization
            - DDD Building Blocks help you with defining implementation details
            
            - **Example**
                - Warehouse Management System - ie software to run a large warehouse. Receives orders, selects inventory, ships products
                - Some 'microservices' in terms of bounded contexts might be:
                    - Inventory
                    - Order Allocation
                    - Manifest (shipping interface with parcel carriers)
                    - Labor Tracking
                    - Returns
                    
        - #### Brewery Monolith Deconstruction
            - **Beer Service**
                - will manage 'Beers' - aka products
                - will manage brewing - aka manufacturing
                - will list beers, and validate order lines for valid beers
                
            - **Beer Order Service**
                - manages Beer Orders
                - will manage the lifecycle of an order - from order placement, to order shipment
                - manages customers
                - listens to order events
                - implements call backs (web hooks) to customers
                
            - **Beer Inventory Service** 
                - manages Beer Inventory
                - takes in inventory from brewing operations
                - provides inventory for orders
                - implementation will be simple
                    - real world would be more complex