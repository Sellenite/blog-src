---
title: Vue增加减少input组件
date: 2017-05-18 23:22:03
tags:
- Vue
- 组件
---
### 用法：

```html
<v-counter @on-change="" :min="" :max=""></v-counter>
```
on-change：每当input里数值改变的时候触发，返回input里的值

min：限制最小值

max：限制最大值

### 子组件源码：

<!--more-->

> template


```html
<template>
  <div class="counter-component">
    <div class="counter-btn" @click="minus"> - </div>
    <div class="counter-show">
      <input type="text" v-model="number" @keyup="numberLimit">
    </div>
    <div class="counter-btn" @click="add"> + </div>
  </div>
</template>
```

> JavaScript


```javascript
export default {
  props: {
    max: {
      type: Number,
      default: 5
    },
    min: {
      type: Number,
      default: 1
    }
  },
  data() {
    return {
      number: this.min
    }
  },
  watch: {
    // 利用数值改变的时候emit
    number() {
      this.$emit('on-change', this.number)
    }
  },
  methods: {
    minus() {
      if (this.number <= this.min)
        this.number = this.min
      else
        this.number--
    },
    add() {
      if (this.number >= this.max)
        this.number = this.max
      else
        this.number++
    },
    numberLimit() {
      let fix
      if (typeof this.number === 'string') {
        // \d表示匹配0-9数字，大写是有区别的，\D表示匹配非0-9数字的字符
        fix = Number(this.number.replace(/\D/g, ''))
      }
      else {
        fix = this.number
      }
      if( fix >= this.max) {
        fix = this.max
      } else if ( fix <= this.min) {
        fix = this.min
      }
      this.number = fix
    }
  }
}
</script>
```

> CSS


```css
<style scoped>
.counter-component {
  position: relative;
  display: inline-block;
  overflow: hidden;
  vertical-align: middle;
}

.counter-show {
  float: left;
}

.counter-show input {
  border: none;
  border-top: 1px solid #e3e3e3;
  border-bottom: 1px solid #e3e3e3;
  height: 23px;
  line-height: 23px;
  width: 30px;
  outline: none;
  text-indent: 4px;
}

.counter-btn {
  border: 1px solid #e3e3e3;
  float: left;
  height: 25px;
  line-height: 25px;
  width: 25px;
  text-align: center;
  cursor: pointer;
}

.counter-btn:hover {
  border-color: #4fc08d;
  background: #4fc08d;
  color: #fff;
}
</style>
```




