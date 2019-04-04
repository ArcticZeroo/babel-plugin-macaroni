# babel-plugin-macaroni

A babel plugin for transforming code into macaroni-supported code.

## What?
- `a + b` becomes `Operator.add(a, b)`
- `a += b` becomes `a = Operator.add(a, b)`
- `++a` becomes `(a = Operator.increment(a))`
- `-a` becomes `Operator.negate(a)`

## Usage

1. Install babel and this node module
2. Add this module as a babel plugin (either with `macaroni` or `babel-plugin-macaroni`, babel will do name normalization)


```typescript
{
    plugins: [
        ['macaroni', { importType: 'require' }]
    ]
}
``` 

You can also pass `skipImport: true` to not import anything when parsing with babel, if you plan to use this in a browser type setting or something, idunno. It was added for unit testing but I'm sure it has some use.

I recommend that macaroni runs before most other transformers, or it may produce unexpected behavior.