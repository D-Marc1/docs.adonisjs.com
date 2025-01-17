Validates the property to be a valid boolean. The string and numeric representations of a boolean are casted to a valid boolean value.

- `"1"`, `1`, `"true"` are casted to `true`
- `"0"`, `0`, `"false"` are casted to `false`

Additionally, we also cast `"on"` to `true` and `"off"` to `false` as these are values the server receives for the HTML checkbox input.

```ts
import { schema } from '@ioc:Adonis/Core/Validator'

{
  accepted: schema.boolean()
}
```

## Mark as optional
You can mark the property to be optional by chaining the `optional` method. Only the `undefined` values are considered optional. We treat `null` as a valid value and it will fail the boolean validation.

```ts
{
  accepted: schema.boolean.optional()
}
```

## Define additional rules
Currently there are no rules for the boolean schema type. However, if you were to create one, then you can pass it as the first argument.

```ts
import { schema, rules } from '@ioc:Adonis/Core/Validator'

{
  title: schema.boolean([
    rules.myCustomRuleForBooleanType(),
  ])
}
```
