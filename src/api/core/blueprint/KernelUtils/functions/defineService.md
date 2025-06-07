[**Core Documentation**](../../../README.md)

***

[Core Documentation](../../../README.md) / [blueprint/KernelUtils](../README.md) / defineService

# Function: defineService()

Defines a service (factory or class) for the Stone.js application.

This utility registers a service in the `stone.services` section of the blueprint.
It supports both factory and class-based service definitions.

## Param

The service class or factory function.

## Param

Service configuration options including alias and factory flag.

## Example

```ts
defineService(MyServiceClass, { alias: 'myService', isClass: true })
defineService((container) => ({ save(){} }), { alias: 'myService' })
```

## Call Signature

> **defineService**(`module`, `options`): `Partial`\<[`StoneBlueprint`](../../../options/StoneBlueprint/interfaces/StoneBlueprint.md)\>

Defined in: [blueprint/KernelUtils.ts:411](https://github.com/stonemjs/core/blob/65c9e07f9d264b07f6e4091fcc29046b5ca8ea45/src/blueprint/KernelUtils.ts#L411)

Defines a factory-based service for the Stone.js application.

### Parameters

#### module

[`FactoryService`](../../../declarations/type-aliases/FactoryService.md)

A factory function that returns the service instance.

#### options

[`ServiceOptions`](../../../declarations/interfaces/ServiceOptions.md) & `object`

Configuration options for the service including alias and factory flag.

### Returns

`Partial`\<[`StoneBlueprint`](../../../options/StoneBlueprint/interfaces/StoneBlueprint.md)\>

A partial StoneBlueprint containing the service metadata.

### Param

The service class or factory function.

### Param

Service configuration options including alias and factory flag.

### Example

```ts
defineService(MyServiceClass, { alias: 'myService', isClass: true })
defineService((container) => ({ save(){} }), { alias: 'myService' })
```

## Call Signature

> **defineService**(`module`, `options`): `Partial`\<[`StoneBlueprint`](../../../options/StoneBlueprint/interfaces/StoneBlueprint.md)\>

Defined in: [blueprint/KernelUtils.ts:423](https://github.com/stonemjs/core/blob/65c9e07f9d264b07f6e4091fcc29046b5ca8ea45/src/blueprint/KernelUtils.ts#L423)

Defines a class-based service for the Stone.js application.

### Parameters

#### module

[`IServiceClass`](../../../declarations/type-aliases/IServiceClass.md)

The service class to be registered.

#### options

[`ServiceOptions`](../../../declarations/interfaces/ServiceOptions.md) & `object`

Configuration options for the service including alias and factory flag.

### Returns

`Partial`\<[`StoneBlueprint`](../../../options/StoneBlueprint/interfaces/StoneBlueprint.md)\>

A partial StoneBlueprint containing the service metadata.

### Param

The service class or factory function.

### Param

Service configuration options including alias and factory flag.

### Example

```ts
defineService(MyServiceClass, { alias: 'myService', isClass: true })
defineService((container) => ({ save(){} }), { alias: 'myService' })
```
