README:

Startup:
Message Broker (MB) is started up. It establishes connection to the Consumer GateWay,eg. SMSC. We simulate this action so far, and make MB and Consumer Gateway get connected 5 seconds after Message Broker started up. If a connection to the Consumer Gateway cannot be established, Message Broker keeps re-trying. Once the connection to the Consumer Gateway is established, MB starts its Producers (Zoom-Gateway) server and starts listening for connections on its incoming TCP port in the range: 7000 to 8000. 

Accepting Producer Connection:
A producer (Zoom-Gateway) sends a TCP connection request to the MB on its TCP port. MB accepts producers and transfers the producer TCP over to a new random port (the random port is assigned by system automatically). MB keeps listening for additional connections.

Handling Producer Connection:
Producer (Zoom-Gateway) sends data to the MB, the thread of ProducerConncectionHandler simply puts the data in the ConsumerService’s centralized queue. The ProducerConnectionHandler assumes no responsibility for consuming the received events.

Consuming the String:
It is completely up to the ConsumerServiceSMS to consume the received events and do something with them.
      
2012-10-22  
New feature: added google protocol buffer 

2012-11-14  
New feature: versionaire is added

2012-11-20

