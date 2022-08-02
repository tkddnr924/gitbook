---
description: https://vuetifyjs.com/en/
---

# Vuetify 사용

## 시작하기 (설치)

```
npm install vuetify
npm install sass sass-loader fibers deepmerge -D
```

### Webpack.config.js

{% code title="webpack.config.js" %}
```javascript
module.exports = {
  rules: [
    {
      test: /\.s(c|a)ss$/,
      use: [
        'vue-style-loader',
        'css-loader',
        {
          loader: 'sass-loader',
          // Requires sass-loader@^7.0.0
          options: {
            implementation: require('sass'),
            fiber: require('fibers'),
            indentedSyntax: true // optional
          },
          // Requires sass-loader@^8.0.0
          options: {
            implementation: require('sass'),
            sassOptions: {
              fiber: require('fibers'),
              indentedSyntax: true // optional
            },
          },
        },
      ],
    },
  ],
}
```
{% endcode %}

### Vuetify.js

{% code title="src/plugins/vuetify.js" %}
```javascript
import Vue from 'vue'
import Vuetify from 'vuetify'
import 'vuetify/dist/vuetify.min.css'

Vue.use(Vuetify)

const opts = {}

export default new Vuetify(opts)
```
{% endcode %}

#### Vuetify-loader 사용중일때

{% code title="src/plugins/vuetify.js" %}
```javascript
import Vue from 'vue'
import Vuetify from 'vuetify/lib'
import 'vuetify/dist/vuetify.min.css'

Vue.use(Vuetify)

const opts = {}

export default new Vuetify(opts)
```
{% endcode %}

### Main.js

{% code title="main.js" %}
```javascript
import Vue from 'vue'
import vuetify from '@/plugins/vuetify' // path to vuetify export

new Vue({
  vuetify,
}).$mount('#app')
```
{% endcode %}

## Vuetify Icon

Material Design Icon 설치

### 설치

```
npm install @mdi/font -D
```

### Vuetify.js

{% code title="src/plugins/vuetify.js" %}
```javascript
import Vue from 'vue'
import Vuetify from 'vuetify'
import 'vuetify/dist/vuetify.min.css'
import '@mdi/font/css/materialdesignicons.css' // CSS 추가

Vue.use(Vuetify)

// 추가
const opts = {
	icons: {
		iconfont: 'mdi' 
	}
}

export default new Vuetify(opts)
```
{% endcode %}

## Reference

1. [https://www.notion.so/Vuetify-cb0548ac3fac4a42baead5c3f7671fe2#f6266a4d8ff84817ac38922f553a70d5](https://www.notion.so/Vuetify-cb0548ac3fac4a42baead5c3f7671fe2#f6266a4d8ff84817ac38922f553a70d5)
