[**AWS Lambda Adapter Documentation v0.0.2**](../../README.md)

***

[AWS Lambda Adapter Documentation](../../modules.md) / [RawHttpResponseWrapper](../README.md) / RawHttpResponseWrapper

# Class: RawHttpResponseWrapper

Defined in: [src/RawHttpResponseWrapper.ts:12](https://github.com/stonemjs/aws-lambda-adapter/blob/9de4b38bb7a5afd4d5599dae1399969698a2422d/src/RawHttpResponseWrapper.ts#L12)

Wrapper for HTTP raw responses in AWS Lambda.

The `RawHttpResponseWrapper` is responsible for constructing and returning
a raw HTTP response that conforms to the expected structure for AWS Lambda.
It implements the `IRawResponseWrapper` interface, ensuring compatibility
with the Stone.js framework.

## Implements

- `IRawResponseWrapper`\<[`RawHttpResponse`](../../declarations/type-aliases/RawHttpResponse.md)\>

## Methods

### respond()

> **respond**(): [`RawHttpResponseOptions`](../../declarations/interfaces/RawHttpResponseOptions.md)

Defined in: [src/RawHttpResponseWrapper.ts:66](https://github.com/stonemjs/aws-lambda-adapter/blob/9de4b38bb7a5afd4d5599dae1399969698a2422d/src/RawHttpResponseWrapper.ts#L66)

Constructs and returns the raw HTTP response.

The `respond` method generates a `RawHttpResponse` object based on the
provided options. If any required fields are missing, it assigns default values:
- `statusCode`: Defaults to `500`.
- `statusMessage`: Defaults to an empty string.
- `body`: Converts non-string bodies to a JSON string.

#### Returns

[`RawHttpResponseOptions`](../../declarations/interfaces/RawHttpResponseOptions.md)

A `RawHttpResponse` object.

#### Example

```typescript
const responseWrapper = RawHttpResponseWrapper.create({ body: 'Hello, world!', statusCode: 200 });
const response = responseWrapper.respond();
console.log(response); // { statusCode: 500, statusMessage: '', body: 'Hello, world!', headers: undefined }
```

#### Implementation of

`IRawResponseWrapper.respond`

***

### create()

> `static` **create**(`options`): [`RawHttpResponseWrapper`](RawHttpResponseWrapper.md)

Defined in: [src/RawHttpResponseWrapper.ts:34](https://github.com/stonemjs/aws-lambda-adapter/blob/9de4b38bb7a5afd4d5599dae1399969698a2422d/src/RawHttpResponseWrapper.ts#L34)

Factory method to create an instance of `RawHttpResponseWrapper`.

This method accepts partial response options, allowing the user to configure
only the required fields. It initializes the wrapper with these options.

#### Parameters

##### options

`Partial`\<[`RawHttpResponseOptions`](../../declarations/interfaces/RawHttpResponseOptions.md)\>

Partial options to configure the HTTP response.

#### Returns

[`RawHttpResponseWrapper`](RawHttpResponseWrapper.md)

A new instance of `RawHttpResponseWrapper`.

#### Example

```typescript
const responseWrapper = RawHttpResponseWrapper.create({
  statusCode: 200,
  body: { message: 'Success' },
  headers: { 'Content-Type': 'application/json' }
});

const response = responseWrapper.respond();
console.log(response); // { statusCode: 200, body: '{"message":"Success"}', headers: { 'Content-Type': 'application/json' } }
```
