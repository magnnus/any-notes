# any-notes
some fleeting thoughts

## the card id generated in bbs post-page

Previously, I use `Date.now()` as the Unique Card Id. But when at some scenarios, multi-generate in one time, it may encount some trouble, repetition.

Maybe I can do like this:

```js
function idMaker() {
  let idx = 1;
  return {
    next() {
      return {
        value: idx++,
        done: false,
      }
    }
  }
}

const it = idMaker();
const currentIdx = it.next().value;
```
