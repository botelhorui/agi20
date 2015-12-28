
One advantage of VPNs is load balancing - when the network starts to degrate, a load balancer can allocate more resources to high priority VPNs.

# Airplane

An airplane is very mobile, so all communication must be over the air - no wires allowed.

1. (LTE) (VPN_PLANE_AIR) Airplane is on air, contacting the airport for landing information. Airport communicates back, plane lands.

2. (LTE / Wi-Fi) (VPN_PLANE_GROUND) The plane has landed. The pilot needs to know where to stop for the passengers to exit and where to park the vehicle.

3. (LTE / Wi-Fi) (VPN_PLANE_GROUND) The plane is parked. On instructions to leave, it goes to the boarding area, then to the right lane and takes off.

VPN_PLANE_AIR is a connection with very high priority - the passengers lives depend on a safe landing.
	
	- Availability: 99.999%
	- Max Latency: 150 ms (at 200m s it gets hard to understand voice communications) 
	- Average Bandwidth: 10Mbs (voice + plane status)

VPN_PLANE_GROUND is a connection with medium priority - the plane is on the ground, maneuvering between lanes and parking spots. If communication is degraded, it will take a few more secs to move the plane around. If communication is lost, a person can run to the plane and assist the pilot.

If the whole area can be covered with Wi-Fi, and the plane can easily connect to it, that would have a better cost/efficiency than LTE.

	- Availability: 99%
	- Max Latency: 300 ms (software can fix high latency problems in relaxed time - transfering audio files  instead of streams, for example)
	- Average Bandwidth: 256 kb/s - 1mb/s (only small communications at this point.

# Traveler

1. (Ethernet) 

 
