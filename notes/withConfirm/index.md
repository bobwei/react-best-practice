# withConfirm

Example Code

```js
export const CONFIRM_SAVE_MSG = 'Are you sure you want to save ?';
export const CONFIRM_DELETE_MSG = 'Are you sure you want to delete ?';

const withConfirm = (confirmMsg = CONFIRM_SAVE_MSG) => (fn) => (...args) => {
  if (window.confirm(confirmMsg)) {
    return fn(...args);
  }
  return Promise.resolve();
};

export default withConfirm;
```

Usage

```
import withConfirm from './withConfirm';

const myFunction = () => {
  console.log('Hello world');
};
const myFunctionWithConfirm = withConfirm()(myFunction);
myFunctionWithConfirm();
```
