# 受控显示
Modal 的显示可以是受控的。
```html
<n-button
  @click="handleClick"
>
  来吧
</n-button>
<n-modal :show="isActive">
  <n-card
    style="width: 600px;"
    title="模态框"
    :bordered="false"
    size="huge"
  >
    倒计时 {{ timeout / 1000 }} 秒
  </n-card>
</n-modal>
```
```js
export default {
  data () {
    return {
      isActive: false,
      timeout: 6000
    }
  },
  methods: {
    handleClick () {
      this.isActive = true
      this.timeout = 6000
      let countdown = () => {
        if (this.timeout <= 0) {
          this.isActive = false
        } else {
          this.timeout -= 1000
          setTimeout(countdown, 1000)
        }
      }
      countdown()
    }
  }
}
```