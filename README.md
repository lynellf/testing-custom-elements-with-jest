# How to test Web Components with Jest
How to test custom elements with Jest without needing Puppeteer

```
$ npm install happy-dom -D
```

### domPolyfill.js
```
import { Window } from 'happy-dom';

const window = new Window();

for (const key of [
  'self',
  'document',
  'HTMLElement',
  'HTMLUnknownElement',
  'customElements'
]) {
  // @ts-ignore
  global[key] = window[key];
}

self.requestAnimationFrame = setTimeout;
```

### test.file.test.js
```
import './domPolyfill'
```

Done. Thank me later.
