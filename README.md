# NetRover32
Long-range ESP32-based rover using a distributed network control system to achieve impressively low latency over very long distances.

# Overview

During my first year of upper secondary school in 2022, I became interested in RC planes and drones. While it was fun flying the aircraft and observing it from the ground or FPV goggles, I always wanted to push the limits and fly extremely far away. It was then I set as a goal to try to achieve control over extreme distances while having a live broadcast. After looking at current market solutions, I was highly dissatisfied and could only be promised a few extra km at the cost of a poor video feed and control. It became obvious to me that direct radio communication would be unideal, especially in more densely populated areas. I decided then and there to develop my own long-distance control system using the biggest network of them all, the Wide Area Network.

# The Distributed Network Control System (DNCS)

It quickly became obvious to me that lightweight communication protocols combined with integrated hardware would result in the best mix of high reliability while at the same time requiring low latency. A low power light weight system would also be very ideal in reaching this result. I also decided early on the most robust setup would be the client (user) pinging command inputs to the server (onboard the vehicle) and then later distributing the commands within the vehicles LAN. Socket.IO became the obvious solution for this as it offers bi directional, low latency and low-overhead communication between server and client. Using websockets and event based communication allows it to be very lightweight aswell and could be seamlessly integrated into a Node.js server. Having Socket.IO as the bridge over the WAN would mean that all commands distributed within the vehicles LAN would be negligent, meaning almost all practical latency in this control system would be between client and server. 
