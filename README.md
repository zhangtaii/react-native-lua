# react-native-lua
> Performant network, database and multithreading solution for react-native, empowered with Lua.

## Motivation

React Naitve provides us the capability to write cross platform APP with single code base, it does meet the expectation in most scenario with not too complicate layouts and low throughout data mutation, but it fails you when building an APP with some high frequence realtime data updating, like the Exchange Trading, Message Chatting.

Under the hood, there is only one JavaScript thread in React Naitve, and that is not good at handling a lot of computation, if JavaScript thread could not finish works for generating a new frame, then stuttering happens.

Another case is too much data passes through the JS-Native Bridge overloads the MessageQueue, likes a jam on the real work road making all traffics slowing down.


As the JavaScript not good at doing IO and computation, let the native codes handle it. The idea behind this project is to delegate these heavy tasks from JS to the native side, reducing the burd of JS Thread. We choose Lua to implement it, which is cross platform, fast and flexible.

Another benifit from this architecture is, the data source could be consumed in both JS and Native side, makes it easier to buid Hybrid APPs with JS and Naitve components involved.


## Other Ideas could done with Lua

* Running a local RPC server to handling HTTP request from JS or Native code, the server side do the data sync, persist, computing jobs, the JS/Native client only need care the result.

* Running a http Proxy server in between APP and BackEnd, handing things of fetching, caching, updating, good for static assets like video/audio, website assets.


