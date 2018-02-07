This Program demo illustrates how to consume the Plantronics Web Services API realtime stream.
It also illustrates how to forward those events (as JSON) onto another REST Service API for 
example to connect to another system.
The events it will look for are QD (quick disconnect) connected/disconnected and Mute (muted/unmuted)
NOTE: In order to work you must edit the .config file in this project (or alongside the EXE) and add
your settings, as follows:
- PubNub_SubscribeKey - this is the PubNub Subscribe key provided for your Plantronics tenant
- PubNub_PublishKey - this is the PubNub Publish key provided for your Plantronics tenant
- PubNub_SubscribeChannel1 - this is the PubNub subscribe channel id 1 provided for your Plantronics tenant
- PubNub_SubscribeChannel2 - this is the PubNub subscribe channel id 2 provided for your Plantronics tenant
- PubNub_SubscribeChannel3 - this is the PubNub subscribe channel id 3 provided for your Plantronics tenant
- PubNub_SubscribeChannel4 - this is the PubNub subscribe channel id 4 provided for your Plantronics tenant
- REST_API_Endpoint - ADD YOUR REST API ENDPOINT HERE TO FORWARD THE EVENT TO
- REST_API_Family - ADD OPTIONAL REST API FAMILY HERE
- REST_API_Type - ADD OPTIONAL REST API TYPE HERE
- REST_API_Version - ADD OPTIONAL REST API VERSION HERE
- SMSNumber - ADD OPTIONAL MOBILE NUMBER HERE TO USE IN YOUR REST API FLOW LATER
- ExtraParams - ADD OPTIONAL EXTRA PARAMETERS HERE TO USE IN YOUR REST API FLOW LATER

Notes:
In the current code implementation, the JSON message forwarded to your REST API Endpoint will include these values:
- SMSNumber - the optional SMSNumber specified in your App.config
- Message - a comma delimited message with Event Type, Time and deviceId of the Plantronics realtime event
- deviceId - a single JSON value for deviceId of the Plantronics realtime event
- Event - a single JSON value for Event Type of the Plantronics realtime event
- Time - a single JSON value for Time stamp of the Plantronics realtime event
- ExtraParams - the optional ExtraParams string specified in your App.config
The JSON message will be sent to your REST API Endpoint within the "eventBody" field of a "multipart/form-data" 
HTTP(S) POST request.
Other fields included are: 
- family - the REST_API_Family specified in your App.config
- type - the REST_API_Type specified in your App.config
- version - the REST_API_Version specified in your App.config
    
Author: Lewis.Collins@Plantronics.com, 6th September 2017
