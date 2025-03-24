- many networks are relatively open on the inside
- Zero trust is a holist approach to network security
	- covers everything
- Everything must be verified
	- Nothing is inherently trusted
## Planes of operation
- Split the network into functional planes
	- Applies to physical, virtual and cloud components
- Data plane
	- Process the frames, packets and network data
	- Processing, forwarding, trunking, encypting, NAT
- Control plane
	- Manages actins of the data plane
	- Define policies and rules
	- Determines how packets should be forwarded
	- Routing tables, session tables, NAT tables

## Controlling trust
- Adaptative identity
	- Consider the source and the requested resources
	- Multiple risk indicators
	- Make authentication stronger
- Threat scope reduction
	- Decrease the number of possible entry points
- Policy-driven access control
	- Combine the adaptative identity with a predefined set of rules

## Security zones
- Security is more than a one-to-one relationship
	- Broad categorizations provide a security-related foundation
- Where are you coming from and where are you going
- Using zones may be enough by itself to deny access

## Policy enforcement point
- subjects and system have to pass through it
- Allow, monitor and terminate connections

## Policy Decision Point
- Police engine: take the decision based on the data gathered by the policy enforcement point
- Policy administrator: Comunicates with the policy enforcement point, generates tokens or credentials, tell PEP to allow or disallow access