# A weird [jest](https://facebook.github.io/jest/) error

## Set up

0. `git clone https://github.com/robinpokorny/weird-jest-error.git`
0. `cd weird-jest-error`
0. [yarn](https://yarnpkg.com/) (or `npm install`)
0. `yarn test` (or `npm test`) — **[First result](#first-result)**
0. Change `index.spec.js` line 19, from `2` to (e.g.) `5`

  ```diff 
  -expect(two).toHaveBeenCalledTimes(2)
  +expect(two).toHaveBeenCalledTimes(5)
  ```
0. `yarn test` (or `npm test`) — **[Second result](#second-result)**

## First result
```
/Users/robin/projects/weird-jest-error/index.spec.js:2
import pubsub from './';
^^^^^^
SyntaxError: Unexpected token import
```

## Second result
```
expect(jest.fn()).toHaveBeenCalledTimes(5)

Expected mock function to have been called five times, but it was called one time.
```

---

### My enviroment
macOS 10.12.2, `node@7.4.0`, `jest@18.1.0`, `yarn@0.17.9`
