---
title: Vue选择单个select组件
date: 2017-05-18 23:33:16
tags:
- Vue
- 组件
---

### 用法：


```html
<v-selection :selections="" @on-change=""></v-selection>
```
selections：绑定的数据，默认格式：

```
buyTypes: [
        {
          label: '入门版',
          value: 0
        },
        {
          label: '中级版',
          value: 1
        },
    ]
```

on-change：选择下拉列表时触发，返回被选择的数据

### 子组件源码：

<!--more-->

> template


```html
<template>
    <div class="selection-component">
      <div class="selection-show" @click="toggleDrop">
        <span>{{ selections[nowIndex].label }}</span>
        <div class="arrow"></div>
      </div>
      <transition name="slideDown">
        <div class="selection-list" v-if="isDrop">
          <ul>
            <li v-for="(item, index) in selections" @click="chooseSelection(index)">{{ item.label }}</li>
          </ul>
        </div>
      </transition>
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
      isDrop: false,
      nowIndex: 0
    }
  },
  methods: {
    toggleDrop () {
      this.isDrop = !this.isDrop;
    },
    chooseSelection (index) {
      this.nowIndex = index;
      this.isDrop = false;
      this.$emit('on-change', this.selections[this.nowIndex]);
    }
  },
  mounted() {
    // 判断如果点击的target不包含在这个组件里的话，就收起列表
    document.addEventListener('click', (e) => {
      if (!this.$el.contains(e.target))
        this.isDrop = false
    }, false);
  }
}
</script>
```

> CSS


```
<style scoped>
.selection-component {
  position: relative;
  display: inline-block;
}
.selection-show {
  border: 1px solid #e3e3e3;
  padding: 0 20px 0 10px;
  display: inline-block;
  position: relative;
  cursor: pointer;
  height: 25px;
  line-height: 25px;
  border-radius: 3px;
  background: #fff;
}
.selection-show .arrow {
  display: inline-block;
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-top: 5px solid #e3e3e3;
  width: 0;
  height: 0;
  margin-top: -1px;
  margin-left: 6px;
  margin-right: -14px;
  vertical-align: middle;
}
.selection-list {
  display: inline-block;
  position: absolute;
  left: 0;
  top: 25px;
  width: 100%;
  background: #fff;
  border-top: 1px solid #e3e3e3;
  border-bottom: 1px solid #e3e3e3;
  z-index: 5;
}
.selection-list li {
  padding: 5px 15px 5px 10px;
  border-left: 1px solid #e3e3e3;
  border-right: 1px solid #e3e3e3;
  cursor: pointer;
  background: #fff;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;

}
.selection-list li:hover {
  background: #e3e3e3;
}

.slideDown-enter-active, .slideDown-leave-active {
  transition: all 0.2s ease;
}

.slideDown-enter, .slideDown-leave-active {
  transform: translateY(-30%);
  opacity: 0;
}
</style>
```






