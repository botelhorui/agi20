
One advantage of VPNs is load balancing - when the network starts to degrate, a load balancer can allocate more resources to high priority VPNs.

# Airplane

An airplane is very mobile, so all communication must be over the air - no wires allowed.

1. (LTE) (VPN_PLANE_AIR) Airplane is on air, contacting the airport for landing information. Airport communicates back, plane lands.

2. (LTE / Wi-Fi) (VPN_PLANE_GROUND) The plane has landed. The pilot needs to know where to stop for the passengers to exit and where to park the vehicle.

3. (LTE / Wi-Fi) (VPN_PLANE_GROUND) The plane is parked. On instructions to leave, it goes to the boarding area, then to the right lane and takes off.

## VPN_PLANE_AIR

VPN_PLANE_AIR is a connection with very high priority - the passengers lives depend on a safe landing.

	- Availability: 99.999%
	- Max Latency: 150 ms (at 200m s it gets hard to understand voice communications)
	- Average Bandwidth: 10Mbs (voice + plane status)

## VPN_PLANE_GROUND

VPN_PLANE_GROUND is a connection with medium priority - the plane is on the ground, maneuvering between lanes and parking spots. If communication is degraded, it will take a few more secs to move the plane around. If communication is lost, a person can run to the plane and assist the pilot.

If the whole area can be covered with Wi-Fi, and the plane can easily connect to it, that would have a better cost/efficiency than LTE.

	- Availability: 99%
	- Max Latency: 300 ms (software can fix high latency problems in relaxed time - transfering audio files  instead of streams, for example)
	- Average Bandwidth: 512 kb/s - 1mb/s (only small communications at this point.

# Traveler

A traveler is mobile, but he also interacts with stationary devices - check-in and flight terminals, security screening machines, etc. Connecting these with ethernet improves their connection quality, but Wi-Fi reduces cabling complexity. **Which one to pick?**

1. Bob, the passenger arrives airport.

2. (Ethernet / Wi-Fi) Bob does the check in. He can proceed if both TICKET_SERVER and SECURITY_SERVER allow it. His luggage is checked in, screened by the SECURITY_SERVER and logged to the RESOURCES_SERVER.

3. (Ethernet / Wi-Fi) Bob checks the flight terminal to know where he will catch his plane.

4. (Ethernet / Wi-Fi) Bob is screened at the security gate. Photos of his hand luggage are sent to SECURITY_SERVER to check for threats. Video footage constantly uploads a video stream to SECURITY_SERVER.

5. (Wi-Fi) (VPN_PUBLIC) Bob connects to the airport Wi-Fi public to check for emails.

6. (Ethernet / Wi-Fi) (VPN_SHOPS + VPN_TRANSACTIONS) Bob goes to a shop and buys a book for the flight.

7. After waiting, Bob boards the plane.

## VPN_PUBLIC

A VPN for personal use by clients and employees. Priority is low.

	- Availability: 90%
	- Max Latency: 1000 ms
	- Average Bandwidth: 256kbs +

## VPN_SHOP

A VPN for shops to access the Internet. Medium priority.

## VPN_TRANSACTIONS

A VPN for money transactions in shops and ATMs. High security and availability are needed. Medium-high priority.

## SECURITY_SERVER

Servers used to handle security. They must receive video streams and process it fast. They must be able to communicate with security personal in case of threats.

## TICKET_SERVER

Servers with ticket info - can't let people without a ticket check in!

## RESOURCES_SERVER

Manages resources - plane parking, luggage moving, etc.
