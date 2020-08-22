# Disallow Large Jest Snapshots Using ESLint

### 08/22/2020

`eslint-plugin-jest` has a handy rule to limit the size of snapshots - `no-large-snapshots`. This is especially useful for maintainability of snapshot tests. Snapshots of a large component are cumbersome to maintain as it requires the dev to have a deep knowledge of this components DOM and contained logic.

[Github - eslint-plugin-jest/no-large-snapshots](https://github.com/jest-community/eslint-plugin-jest/blob/master/docs/rules/no-large-snapshots.md)

Bonus Round: React Native has updated their documentation and added some great [testing guidelines](https://reactnative.dev/docs/testing-overview) for mobile apps.

Tags: JavaScript, React, React Native, Jest, ESLint
