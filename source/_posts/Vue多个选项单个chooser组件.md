---
title: Vue多个选项单个chooser组件
date: 2017-05-18 23:43:50
tags:
- Vue
- 组件
---

### 用法


```html
<v-chooser :selections="" @on-change=""></v-chooser>
```

selections：传入的数据，默认格式：


```
  periodList: [
    {
      label: '半年',
      value: 0
    },
    {
      label: '一年',
      value: 1
    },
]
```

on-change：点击选择的时候触发，返回被选择的数据

### 子组件源码：

<!--more-->

> template


```html
<template>
    <div class="chooser-component">
        <ul class="chooser-list">
          <li
          v-for="(item, index) in selections"
          @click="chosenSelection(index)"
          :title="item.label"
          :class="{active:index === nowIndex}"
          >{{ item.label }}</li>
        </ul>
      </div>
    </div>
</template>
```

> JavaScript

```javascript
<script>
export default {
  props: {
    selections: {
      type: Array,
      default: [{
        label: 'test',
        value: 0
      }]
    }
  },
  data () {
    return {
      nowIndex: 0
    }
  },
  methods: {
    chosenSelection (index) {
      this.nowIndex = index
      this.$emit('on-change', this.selections[index])
    }
  }
}
</script>
```

> CSS

```css
<style scoped>
.chooser-component {
  position: relative;
  display: inline-block;
}
.chooser-list li{
  display: inline-block;
  border: 1px solid #e3e3e3;
  height: 25px;
  line-height: 25px;
  padding: 0 8px;
  margin-right: 5px;
  border-radius: 3px;
  text-align: center;
  cursor: pointer;
}
.chooser-list li.active {
  border-color: #4fc08d;
  background: #4fc08d;
  color: #fff;
}
</style>
```






