![](https://cloud.githubusercontent.com/assets/8536244/19581841/ad4ff6de-9762-11e6-873b-209eb00de863.jpg)

#### install

```js
npm install bream
```

#### usage
```js
import { Scream, Brim } from 'bream'

const mask = document.querySelector('#brim-mask')
const main = document.querySelector('#brim-main')

try {
  // Here for iOS
  const brim = new Brim(window, {
    viewport: Scream({
      width: {
        portrait: window.screen.width,
        landscape: window.screen.height,
      },
    }),
  })
  mask.innerHTML = '<h1>Main is hidden!!</h1>'
  brim.on('viewchange', e => {
    if (e.viewName === 'minimal') {
      setTimeout(() => {
        main.style.height = (parseInt(main.style.height) - 44) + 'px'
      }, 0)
    }
  })
} catch (e) {
  // Here for others
  console.log(e.message)
  document.body.removeChild(mask)
  document.querySelector('meta[name="viewport"]').setAttribute('content', [
    'width=device-width',
    'initial-scale=1.0',
    'maximum-scale=1.0',
    'user-scalable=0',
  ].join(','))
}
```

#### author

[gajus/brim](https://github.com/gajus/brim)