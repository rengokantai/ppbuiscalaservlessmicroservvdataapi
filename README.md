# ppbuiscalaservlessmicroservvdataapi
## The Course Overview
Containers
- Benefits
  - Ship code and dependencies in a portable container
  - OS level virtualization
  - Good use of available resources
  - Immutable container images
- Drawback
  - Scales in seconds
  - Cluster and image configuration, and maintaince effort
  - Integration effort with other AWS managed services
  - Pay for idle containers


hand write a condition
```
{
  "Version":"2012-12-07",
  "Statement": {
    "Effect":"Allow",
    "Action":["dynamodb:GetItem",
    "dynamodb:Scan",
    "dynamodb:Query"],
    "Resource":"arn:aws:dynamodb:us-west-1:123:table/book",
    "Condition":{
      "IpAddress":{
        "aws:SourceIp":"1.2.3.4/16"
      }
    }
  }
}
```

### Monolithic and Microservice
service oriented architecture
- Built as single code base
- More granular than multi-tier
- Standardised service contracts and registry
- Autonomy and Abstraction
- Smart data pipeline and/or middleware
- https://

### Setting Up a Lambda in the AWS Management Console
```
import json
def respond(err,res=None):
  return {
    'statusCode': '400' if err else '200',
    'body':err.message if err else json.dumps(res),
    'headers': {
      'Content-Type':'application/json',
    },
  }
def parse_parameter(event):
  try:
    returnParameters = event['queryStringParameters'].copy()
  except Exception as e:
    returnParameters = {}
  try:
  
def lambda_handler(event,context):
  validated_parameters = parse_parameters(event)
  if validated_parameters['err'] is not None:
    return respond(validated_parameters['err'])
  else:
    return respond(None,validated_parameters.get('parsedParams',None))
  




