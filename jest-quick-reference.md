 Quick Reference

- [Test structure](#test-structure)
- [Matchers](#matchers)
  - [Basic matchers](#basic-matchers)
  - [Truthiness](#truthiness)
  - [Numbers](#numbers)
  - [Strings](#strings)
  - [Arrays](#arrays)
  - [Objects](#objects)
  - [Exceptions](#exceptions)
  - [Snapshots](#snapshots)
  - [Mock functions](#mock-functions)
  - [Misc](#misc)
  - [Promise matchers (Jest 20+)](#promise-matchers-jest-20)
- [Async tests](#async-tests)
  - [async/await](#asyncawait)
  - [Promises](#promises)
  - [done() callback](#done-callback)
- [Mocks](#mocks)
  - [Mock functions](#mock-functions-1)
  - [Returning, resolving and rejecting values](#Returning-resolving-and-rejecting-values)
  - [Mock modules using `jest.mock` method](#mock-modules-using-jestmock-method)
  - [Mock modules using a mock file](#mock-modules-using-a-mock-file)
  - [Mock object methods](#mock-object-methods)
  - [Mock getters and setters (Jest 22.1.0+)](#mock-getters-and-setters-jest-2210)
  - [Mock getters and setters](#mock-getters-and-setters)
  - [Clearing and restoring mocks](#clearing-and-restoring-mocks)
  - [Accessing the original module when using mocks](#accessing-the-original-module-when-using-mocks)
  - [Timer mocks](#timer-mocks)
- [Data-driven tests (Jest 23+)](#data-driven-tests-jest-23)
- [Skipping tests](#skipping-tests)
- [Testing modules with side effects](#testing-modules-with-side-effects)

## Basic Test Structure

```js
describe('Color Picker', () => {
  beforeAll(() => {
    /* Runs before all tests */
  })
  afterAll(() => {
    /* Runs after all tests */
  })
  beforeEach(() => {
    /* Runs before each test */
  })
  afterEach(() => {
    /* Runs after each test */
  })
  
  test('Choose a color', () => {
    const actual = fn(['Alice', 'Bob', 'Eve'])
    expect(actual).toEqual(['Pink Alice', 'Pink Bob', 'Pink Eve'])
  })
})
```

## Matchers

[Using matchers](http://jestjs.io/docs/en/using-matchers), [matchers docs](https://facebook.github.io/jest/docs/expect.html)

### Basic matchers

```js
expect(42).toBe(42) // Strict equality (===)
expect(42).not.toBe(3) // Strict equality (!==)
expect([1, 2]).toEqual([1, 2]) // Deep equality
expect({ a: undefined, b: 2 }).toEqual({ b: 2 }) // Deep equality
expect({ a: undefined, b: 2 }).not.toStrictEqual({ b: 2 }) // Strict equality (Jest 23+)
```

### Truthiness

```js
// Matches anything that an if statement treats as true (not false, 0, '', null, undefined, NaN)
expect('foo').toBeTruthy()
// Matches anything that an if statement treats as false (false, 0, '', null, undefined, NaN)
expect('').toBeFalsy()
// Matches only null
expect(null).toBeNull()
// Matches only undefined
expect(undefined).toBeUndefined()
// The opposite of toBeUndefined
expect(7).toBeDefined()
// Matches true or false
expect(true).toEqual(expect.any(Boolean))
```

### Numbers

```js
expect(2).toBeGreaterThan(1)
expect(1).toBeGreaterThanOrEqual(1)
expect(1).toBeLessThan(2)
expect(1).toBeLessThanOrEqual(1)
expect(0.2 + 0.1).toBeCloseTo(0.3, 5)
expect(NaN).toEqual(expect.any(Number))
```

### Strings

```js
expect('long string').toMatch('str')
expect('string').toEqual(expect.any(String))
expect('coffee').toMatch(/ff/)
expect('pizza').not.toMatch('coffee')
expect(['pizza', 'coffee']).toEqual([expect.stringContaining('zz'), expect.stringMatching(/ff/)])
```

### Arrays

```js
expect([]).toEqual(expect.any(Array))
expect(['Alice', 'Bob', 'Eve']).toHaveLength(3)
expect(['Alice', 'Bob', 'Eve']).toContain('Alice')
expect([{ a: 1 }, { a: 2 }]).toContainEqual({ a: 1 })
expect(['Alice', 'Bob', 'Eve']).toEqual(expect.arrayContaining(['Alice', 'Bob']))
```

### Objects

```js
expect({ a: 1 }).toHaveProperty('a')
expect({ a: 1 }).toHaveProperty('a', 1)
expect({ a: { b: 1 } }).toHaveProperty('a.b')
expect({ a: 1, b: 2 }).toMatchObject({ a: 1 })
expect({ a: 1, b: 2 }).toMatchObject({
  a: expect.any(Number),
  b: expect.any(Number)
})
expect([{ a: 1 }, { b: 2 }]).toEqual([
  expect.objectContaining({ a: expect.any(Number) }),
  expect.anything()
])
```

### Exceptions

```js
// const fn = () => { throw new Error('Out of cheese!') }
expect(fn).toThrow()
expect(fn).toThrow('Out of cheese')
expect(fn).toThrowErrorMatchingSnapshot()
```

### Snapshots

```js
expect(node).toMatchSnapshot()
// Jest 23+
expect(user).toMatchSnapshot({
  date: expect.any(Date)
})
expect(user).toMatchInlineSnapshot()
```

### Mock functions

```js
// const fn = jest.fn()
// const fn = jest.fn().mockName('Unicorn') -- named mock, Jest 22+
expect(fn).toBeCalled() // Function was called
expect(fn).not.toBeCalled() // Function was *not* called
expect(fn).toHaveBeenCalledTimes(1) // Function was called only once
expect(fn).toBeCalledWith(arg1, arg2) // Any of calls was with these arguments
expect(fn).toHaveBeenLastCalledWith(arg1, arg2) // Last call was with these arguments
expect(fn).toHaveBeenNthCalledWith(args) // Nth call was with these arguments (Jest 23+)
expect(fn).toHaveReturnedTimes(2) // Function was returned without throwing an error (Jest 23+)
expect(fn).toHaveReturnedWith(value) // Function returned a value (Jest 23+)
expect(fn).toHaveLastReturnedWith(value) // Last function call returned a value (Jest 23+)
expect(fn).toHaveNthReturnedWith(value) // Nth function call returned a value (Jest 23+)
expect(fn.mock.calls).toEqual([['first', 'call', 'args'], ['second', 'call', 'args']]) // Multiple calls
expect(fn.mock.calls[0][0]).toBe(2) // fn.mock.calls[0][0] — the first argument of the first call
```

<details>
  <summary>Aliases</summary>

- `toBeCalled` → `toHaveBeenCalled`
- `toBeCalledWith` → `toHaveBeenCalledWith`
- `lastCalledWith` → `toHaveBeenLastCalledWith`
- `nthCalledWith` → `toHaveBeenNthCalledWith`
- `toReturnTimes` → `toHaveReturnedTimes`
- `toReturnWith` → `toHaveReturnedWith`
- `lastReturnedWith` → `toHaveLastReturnedWith`
- `nthReturnedWith` → `toHaveNthReturnedWith`
  </details>

### Misc

```js
expect(new A()).toBeInstanceOf(A)
expect(() => {}).toEqual(expect.any(Function))
expect('pizza').toEqual(expect.anything())
```

### Promise matchers (Jest 20+)

```js
test('resolve to lemon', () => {
  expect.assertions(1)
  // Make sure to add a return statement
  return expect(Promise.resolve('lemon')).resolves.toBe('lemon')
  return expect(Promise.reject('octopus')).rejects.toBeDefined()
  return expect(Promise.reject(Error('pizza'))).rejects.toThrow()
})
```

Or with async/await:

```js
test('resolve to lemon', async () => {
  expect.assertions(2)
  await expect(Promise.resolve('lemon')).resolves.toBe('lemon')
  await expect(Promise.resolve('lemon')).resolves.not.toBe('octopus')
})
```

[resolves docs](https://facebook.github.io/jest/docs/en/expect.html#resolves)

## Async tests

See [more examples](https://facebook.github.io/jest/docs/en/tutorial-async.html) in Jest docs.

It’s a good practice to specify a number of expected assertions in async tests, so the test will fail if your assertions weren’t called at all.

```js
test('async test', () => {
  expect.assertions(3) // Exactly three assertions are called during a test
  // OR
  expect.hasAssertions() // At least one assertion is called during a test

  // Your async tests
})
```
Note that you can also do this per file, outside any `describe` and `test`:
```js
beforeEach(expect.hasAssertions)
```
This will verify the presense of at least one assertion per test case. It also plays nice with more specific `expect.assertions(3)` declarations.

### async/await

```js
test('async test', async () => {
  expect.assertions(1)
  const result = await runAsyncOperation()
  expect(result).toBe(true)
})
```