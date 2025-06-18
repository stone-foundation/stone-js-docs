# Type Alias: AwsLambdaEventHandlerFunction()\<RawResponseType\>

```ts
type AwsLambdaEventHandlerFunction<RawResponseType> = (rawEvent, context) => Promise<RawResponseType>;
```

Represents an AWS Lambda event handler function.

## Type Parameters

### RawResponseType

`RawResponseType` = [`RawResponse`](RawResponse.md)

The type of the response returned by the handler.

## Parameters

### rawEvent

[`AwsLambdaEvent`](AwsLambdaEvent.md)

The raw event received by the AWS Lambda function.

### context

[`AwsLambdaContext`](AwsLambdaContext.md)

The AWS Lambda execution context.

## Returns

`Promise`\<`RawResponseType`\>

A promise resolving to the response of type `RawResponseType`.
