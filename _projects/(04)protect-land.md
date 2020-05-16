---
name: Protect Land
tools: [Software Development, UI/UX Design, Mapping]
image: /assets/images/projects/project-protectland-01.png
description: A web app that displays protected land within a short drive and encourages users to support conservation.
---

# Protect Land

This web app bridges the gap between new technology and nonprofit development to create a unique marketing, development, and community engagement tool for a conservation organization.

![Protect Land](/assets/images/projects/project-protectland-01.png)

When people communicate distances and location they often use time in place of other measurements. “The store is a 10 minute drive away.” vs “The store is 7.2 miles away.” Using a mapping technique called an [isochrone](https://wiki.openstreetmap.org/wiki/Isochrone), we can visually show that time as a shape on the map.

I combined this concept with preserved land areas to create a website that shows a user preserved land within a 5 minute drive of an address they enter. The result page shows a map with preserved land and the drive time shape. A message displays based on the count of preserved land within the drive time shape and prompts the user to take action.

The web app is designed to work on any mobile device, tablet, or computer, so it’s easily accessible and sharable.

## Tech

I built the main functionality of Protect Land using JavaScript, leveraging several open source tools.

The web app loads a simple interface that prompts the user to enter an address.

To learn more about how I created the opening page with an address search box, [check out this blog post](/blog/separate-Mapbox-address-search).

Mapbox GL JS, Turf JS, Mapbox Isochrone API, Mapbox Geocoder

## Goals

- Help a conservation nonprofit raise funds or increase membership
- Create a fun and easy-to-use app for a wide community of users. Basic functionality makes the app quick to use and encourages link sharing.
- Design a tool with accessibility in mind. High contrast colors are friendly for vision impaired users.

## Results

- Create buzz about conservation through social sharing
- Raise funds or register members via the call to action
- Elevate Heritage Conservancy’s position as an innovator in the development space ⇒ encourage future donors and business sponsors to support Heritage Conservancy initiatives

<p class="text-center">
{% include elements/button.html link="http://protectland.danford.us" text="Try the app" %}
</p>
