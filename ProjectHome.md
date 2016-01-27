Open-source Webservice class implementation in AS3 for Flash CS3 IDE.

Download [\*.mxp extension here](http://as3webservice.googlecode.com/svn/trunk/build/as3webservice.zip).

Browse [source here](http://code.google.com/p/as3webservice/source/checkout).

Example code:
```
import be.wellconsidered.services.WebService;
import be.wellconsidered.services.Operation;

import be.wellconsidered.services.events.OperationEvent;

var ws = new WebService("http://www.webservicex.net/WeatherForecast.asmx?wsdl");
var op:Operation = new Operation(ws);

op.addEventListener(OperationEvent.COMPLETE, onResult);
op.addEventListener(OperationEvent.FAILED, onFault);

op.GetWeatherByPlaceName("new york");  

function onResult(e:OperationEvent):void { trace(e.data); }
function onFault(e:OperationEvent):void { trace(e.data); }
```