# jest-module-field-resolver

This package is for jest to use packages that don't have `main` field in their
package.json.

## Usage

1. install the package

   ```
   $ npm i -D jest-module-field-resolver
   ```

2. add `jest-module-field-resolver` as the resolver of jest, and
   `transformIgnorePattern` so that the package missing `main` field can be
    transpiled correctly when running jest.

   In your package.json, please add them as follows:

   ```json
   {
     ...
     "jest": {
       ...
       "transformIgnorePattern": "node_modules/(?!(package_1|package_2)/)",
       "resolver": "jest-module-field-resolver"
     }
   }
   ```