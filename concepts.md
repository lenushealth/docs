# Platform Concepts

![](concepts.jpg?raw=true)

## Client

A _Client_ is a piece of software, written by a third-party developer, that interacts with the Lenus platform.

Example Clients include:

- blood-pressure iPhone app
- health professional website
- data analysis and publishing service

## Samples

A _Sample_ is a represents a piece health data for a user for some time.

Example Samples include:

- heart-rate of a user at an instant
- number of steps a user took between between two instants
- nutritional values of food a user consumed on a day
- sleep quality of a user on a night

## DataServer

The _DataServer_ stores Samples.

The DataServer is used by developers' Clients to read and write Samples via an API. API calls must be authorized to succeed. Authorization is a based on user granted permission for the Client making a call.

## IdentityServer

The _IdentityServer_ provides services to authenticate users' identities, and controls authorization for Clients accessing the DataServer.

## Agency

A user with the approprate permission may request access to another user's identifying information and Samples. If this request is granted, the requesting user is said to have _Agency_ over the other.
