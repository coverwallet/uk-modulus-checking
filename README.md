# uk-modulus-checking

Modulus checking allows payment originators to confirm that customer codes and account numbers are compatible before submitting a Bacs Direct Credit of Direct Debit.

## Installation

Install the package via `npm`:

```sh
npm cowervallet/install uk-modulus-checking
```

## Keep updated

Information in data folder should be always updated based on new [Modules checking rules](https://www.vocalink.com/tools/modulus-checking/).

## Usage

### `new UkModulusChecking({ accountNumber, sortCode }).isValid()`

This method validates if the given accountNumber and sortCode represent a valid `Faster Payment Account`.

#### Arguments

1. `accountNumber` _(string)_: The account number to validate.
2. `sortCode` _(string)_: The sort code to validate.

#### Returns

_(boolean)_: Returns `true` if the account is valid.

#### Example

```js
new UkModulusChecking({ accountNumber: '15764273', sortCode: '938063' }).isValid();
// => false

new UkModulusChecking({ accountNumber: '66374958', sortCode: '089999' }).isValid();
// => true

new UkModulusChecking({ accountNumber: '66374958', sortCode: '08-99-99' }).isValid();
// => true

new UkModulusChecking({ accountNumber: '66374958', sortCode: '08-9999' }).isValid();
// => true
```

## Tests

```sh
npm test
```

## License

MIT

## Credits

Many thanks to [bazerk/uk-modulus-checking](https://github.com/bazerk/uk-modulus-checking) for the original inspiration.

[npm-image]: https://img.shields.io/npm/v/uk-modulus-checking.svg?style=flat-square
[npm-url]: https://npmjs.org/package/uk-modulus-checking
[travis-image]: https://img.shields.io/travis/uphold/uk-modulus-checking.svg?style=flat-square
[travis-url]: https://img.shields.io/travis/uphold/uk-modulus-checking.svg?style=flat-square
