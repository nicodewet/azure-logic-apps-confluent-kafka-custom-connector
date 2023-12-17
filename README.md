# azure-logic-apps-confluent-kafka-custom-connector

This repo contains the steps needed to create a Custom Azure Logic Apps connector that can publish to 
a Kafka topic on Confluent Cloud.

## The Steps

### Get an Open API 2.0 Specification with /records and /records:batch POST support

At the time of writing, Dec '23, Azure Logic Apps only supports [Open API 2.0 specifications](https://swagger.io/specification/v2/), and the Kafka REST Proxy specification is an [Open API 3.0 specification](https://github.com/confluentinc/kafka-rest/blob/master/api/v3/openapi.yaml).

This step has already been done for you, you can simply download the [REST Admin API-Swagger20.json file](API_specifications/REST Admin API-Swagger20.json)

I created this file as follows:

1. Given that we only want to use two methods to publish Kafka messages/events produce a [smaller OpenAPI specification] from a [local copy](API_specifications/openapi.yaml) of the [source specification](https://github.com/confluentinc/kafka-rest/blob/master/api/v3/openapi.yaml).

2. Use [APIMatic](https://www.apimatic.io/) to auto downgrade from the much smaller Open API 3.0 specification that I produced by hand to what is now an [Open API 2.0 specification](API_specifications/REST Admin API-Swagger20.json).

### Create the custom connector

Here you'll follow the official guide on how to [Create a custom connector from an OpenAPI definition](https://learn.microsoft.com/en-us/connectors/custom-connectors/define-openapi-definition).

### Use the custom connector

TODO.


