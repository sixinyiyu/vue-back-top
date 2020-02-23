# back-top

A back top component for vue.js.

## Install

**NPM**

```shell
npm install @mlqt/vue-back-top
```

## Usage

Use **`<back-top/>`** to enable the scroll to the top, and use **props** to define its options.

When the scroll bar height is greater than 100vh, **back-top** is display, otherwise hidden.

```html
<back-top color="#409EFF" :size="1.1" :slow="10"> </back-top>

<!-- Replace the default icon with slot -->
<back-top>
    <div>Icon</div>
</back-top>
```

```javascript
import Vue from 'vue'
import BackTop from '@mlqt/vue-back-top'

Vue.use(BackTop)

new Vue().$mount('#app')
```

## Options

| Props  | Description                                                  | **Required** | Type   | Default |
| ------ | ------------------------------------------------------------ | ------------ | ------ | ------- |
| right  | Back-top distance to the right                               | false        | String | 3%      |
| bottom | Back-top distance to the bottom                              | false        | String | 20%     |
| color  | Back-top color                                               | false        | String | #409EFF |
| size   | Back-top size                                                | false        | Number | 1       |
| slow   | Back-top The speed of scrolling, the larger the value, the slower the scrolling | false        | Number | 10      |




## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/molvqingtai/vue-back-top/blob/master/LICENSE) file for details


### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
