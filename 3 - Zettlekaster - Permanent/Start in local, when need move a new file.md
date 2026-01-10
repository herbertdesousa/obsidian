Date: 2025-04-22
Tags: [[KISS]], [[Start Simple, Complex when you need]]

When you are creating something like a function to create a mock for a test, function to calculate something... Make them locally first. 
Good example:
```ts
const createUnderwriting = (overrides?: Partial<Underwriting>) =>
      Underwriting.instance({
        id: faker.datatype.uuid(),
        initialPrice: new Decimal(10),
        currentToken: new Decimal(1000),
        ...overrides,
      });
```
Simple function to create a mock of an underwriting for a test... But if it turns useful for other tests you may want to create a **fixture** to be reusable!

But, if the function is like: join two arrays, sum numbers... probably they are too *util* for some others scenario. Be fair.