+++
date = "2015-11-23T13:45:50+01:00"
draft = true
link = "https://github.com/SamuelDebruyn/AD5-Cirqus-demo"
technology = ".NET"
title = "Cirqus demo"

+++

In my graduation year I had to demonstrate how you can implement the CQRS principle in .NET. I went looking for a few CQRS frameworks and I found [Cirqus](https://github.com/d60/Cirqus). It's the easiest way to get started with [CQRS](http://martinfowler.com/bliki/CQRS.html) and [event sourcing](https://msdn.microsoft.com/en-us/library/dn589792.aspx) in .NET.

I then developed this simple project which demonstrates the basic concepts of [domain driven design](http://dddcommunity.org/learning-ddd/what_is_ddd/), CQRS and event sourcing using Cirqus.

## Domain

The project is about a hotel called *Oditel* (our school was called *Odisee*...). There are 3 contexts with their aggregate roots:

* Room
* Customer
* Booking

The project has the following layers:

* Domain: models and services (interfaces)
* Infrastructure: everything related to Cirqus, implementations of the services
* Presentation: this layer isn't really a complete layer. It's just a simple console app to demonstrate how the domain and infrastructure layers work.

The application and presentation layers were out of the scope of this project.

The console app goes through the followings steps:

1. Create 4 rooms
1. Create 2 customers
1. Let a customer book 2 rooms
1. Remove the booking

## Extra features

The events and most important *views* are stored in SQL Server (Local DB).

There is an extra view that keeps statistics of bookings per room per quarter. This view is rendered to **MongoDB**, so you also need a local MongoDB server.

There are a few code diagrams to visualize how each layer interacts with the other layers.

I created 4 branches with the 4 steps you have to take when developing a domain driven designed project.

## Slides

With that demo also goes a presentation (in Dutch) which you can download [right here](https://onedrive.live.com/redir?resid=B5240A36EC9AE039!485572&authkey=!AFa6VJYzeHPv4hI&ithint=file%2cpptx). Let me know if the link is broken (I tend to move my files in my OneDrive around quite a lot).