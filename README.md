 
    Title: Lightning Micropayment Server
    Authors: Christian Moss
    Created: 2019-03-03


# Abstract

A Golang based server utilizing websockets to allow streaming of micropayments between a game/app and lightning network wallet

* Can be easily self hosted by a game or app developer
* Utilize direct websockets and or webRTC to allow instant streaming of payments between a game/app and users wallet
* Compatible with LND implementation


# Motivation

One of the largest potential use cases for the lightning network is micropayments in gaming, for example users can battle each other in a street fighter battle type game trading hits for satoshis, or milli satoshis could be used as ammo in a first person shooter type game. An Ingress geo caching style game could allow users to collect satoshis as they walk etc. However with current implementations of the lightning network this is not possible for two reasons

1. The current implementation is based around an invoice model where invoices are generated and paid, this is suitable for a commerce/paywall type of application but not for a streaming service.

2. Any micropayment controller is best separated from the lightning node as game developers do not want their game to directly communicate with their node rather a middleware server is needed to give the developer better security, customization and obfuscation.


#### Example
A proof of concept can be seen below, however this is a demo and a more thought out solution would feature faster payments.
https://www.youtube.com/watch?v=c8NvwWH40Ys



# Implementation
A few different parts are needed for the solution to work

1. Golang/node-js server side app which sits as a middleware between the lightning node, game and user wallet controlling the main flow of payments between them


2. Game/App plugin to allow the games/apps to communicate with the lightning micropayment server e.g. Unity 3D plugin


3. Client/user side wallet plugin to allow mobile wallets to also communicate with the game via the lightning micropayment server i.e. iOS/android sdk for mobile, node-js library for web and desktop wallets

# Goal
The main goal of the project is to allow any game or app developer without advanced knowledge of the lightning network to allow micropayment real time streaming between their game/app and the user to unlock a new range of game and app use cases.
To simplify the installation of the micropayment server it could even be compatible with BTCPay server and deployable in a "one click to install" mechanism

# Copyright

This document is placed in the public domain.
