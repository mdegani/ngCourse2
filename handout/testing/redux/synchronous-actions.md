# Testing Synchronous Actions

Recall that by synchronous we mean action creators that return a simple JSON object, like the first two counter actions in [angular2-redux-starter](https://github.com/rangle/angular2-redux-starter).   

```js

export const INCREMENT_COUNTER = 'INCREMENT_COUNTER';
export const DECREMENT_COUNTER = 'DECREMENT_COUNTER';

export function increment() {
  return {
    type: INCREMENT_COUNTER
  };
}

export function decrement() {
  return {
    type: DECREMENT_COUNTER
  };
}

...

```

These are pretty straightforward to test.

```js

import {INCREMENT_COUNTER, DECREMENT_COUNTER} from './counter';
import * as CounterActions from './counter';

describe('counter action creators', () => {                     
  it('increment should create INCREMENT_COUNTER action', () => {
    expect(CounterActions.increment())                     
      .toEqual({                                          
        type: INCREMENT_COUNTER                                 
      });                                                       
  });                                                           

  it('decrement should create DECREMENT_COUNTER action', () => {
    expect(CounterActions.decrement())                     
      .toEqual({                                          
        type: DECREMENT_COUNTER                                 
      });                                                       
  });                                                           

  ...

});                                                             
```

We just make sure that our action creators do indeed create actions.
