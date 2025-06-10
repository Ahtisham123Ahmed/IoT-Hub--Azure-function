# IoT-Hub--Azure-function
Indesx file  : 
module.exports = function (context, IoTHubMessages) {
    context.log(`JavaScript eventhub trigger function called for message array: ${IoTHubMessages}`);
    
    IoTHubMessages.forEach(message => {
        context.log(`Processed message: ${message}`);
    });

    context.done();
};

Function code
{
  "bindings": [
    {
      "type": "eventHubTrigger",
      "name": "IoTHubMessages",
      "direction": "in",
      "eventHubName": "samples-workitems",
      "connection": "Energy-Meter-Enfana_events_IOTHUB",
      "cardinality": "many",
      "consumerGroup": "$Default",
      "dataType": "string"
    }
  ]
}
