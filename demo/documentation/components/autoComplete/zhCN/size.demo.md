# 尺寸
```html
<n-auto-complete :options="options" v-model="value" placeholder="邮箱" size="small" />
<n-auto-complete :options="options" v-model="value" placeholder="邮箱" size="medium" />
<n-auto-complete :options="options" v-model="value" placeholder="邮箱" size="large" />
```
```js
export default {
  computed: {
    options () {
      return [
        '@gmail.com',
        '@163.com',
        '@qq.com'
      ].map(suffix => {
        const prefix = this.value.split('@')[0]
        return {
          label: prefix + suffix,
          value: prefix + suffix,
        }
      })
    }
  },
  data () {
    return {
      value: ''
    }
  }
}
```
```css
.n-auto-complete {
  margin-bottom: 8px;
}
```