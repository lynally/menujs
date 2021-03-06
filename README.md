# Vue Contextmenu

原来的右键触发，改成左键触发了。
安装和配置和原组件相同。



## CDN
```html
<script src="https://unpkg.com/vue-contextmenujs/dist/contextmenu.umd.js">
```


# 使用
CDN引入则不需要 `Vue.use(Contextmenu)`
> 测试中使用的是`element-ui`图标
```js
import Contextmenu from "vue-contextmenujs"
Vue.use(Contextmenu);
```


```html
<template>
  <div id="app" style="width:100vw;height:100vh" @contextmenu.prevent="onContextmenu"></div>
</template>

<script>
export default {
  methods: {
    onContextmenu(event) {
      this.$contextmenu({
        items: [
          {
            label: "返回(B)",
            onClick: () => {
              this.message = "返回(B)";
              console.log("返回(B)");
            }
          },
          { label: "前进(F)", disabled: true },
          { label: "重新加载(R)", divided: true, icon: "el-icon-refresh" },
          { label: "另存为(A)..." },
          { label: "打印(P)...", icon: "el-icon-printer" },
          { label: "投射(C)...", divided: true },
          {
            label: "使用网页翻译(T)",
            divided: true,
            minWidth: 0,
            children: [{ label: "翻译成简体中文" }, { label: "翻译成繁体中文" }]
          },
          {
            label: "截取网页(R)",
            minWidth: 0,
            children: [
              {
                label: "截取可视化区域",
                onClick: () => {
                  this.message = "截取可视化区域";
                  console.log("截取可视化区域");
                }
              },
              { label: "截取全屏" }
            ]
          },
          { label: "查看网页源代码(V)", icon: "el-icon-view" },
          { label: "检查(N)" }
        ],
        event,
        //x: event.clientX,
        //y: event.clientY,
        customClass: "class-a",
        zIndex: 3,
        minWidth: 230
      });
      return false;
    }
  }
};
</script>
```


# 参数说明

## Menu

| 属性 | 描述 | 类型 | 可选值 | 默认值 |
| :----: | :----: | :----: | :----: | :----: |
| items | 菜单结构信息 | `MenuItem[]` | — | — |
| event | 鼠标事件信息 | `Event` | — | — |
| x | 菜单显示X坐标, 存在`event`则失效 | `number` | — | `0` |
| y | 菜单显示Y坐标, 存在`event`则失效 | `number` | — | `0` |
| zIndex | 菜单样式`z-index` | `number` | — | `2` |
| customClass | 自定义菜单class | `string` | — | — |
| minWidth | 主菜单最小宽度 | `number` | — | `150` |

## MenuItem

| 属性 | 描述 | 类型 | 可选值 | 默认值 |
| :----: | :----: | :----: | :----: | :----: |
| label | 菜单项名称 | `string` | — | — |
| icon | 菜单项图标, 生成`<i class="icon"></i>`元素 | `string` | — | — |
| disabled | 是否禁用菜单项 | `boolean` | — | `false` |
| divided | 是否显示分割线 | `boolean` | — | `false` |
| customClass | 自定义子菜单class | `string` | — | — |
| minWidth | 子菜单最小宽度 | `number` | — | `150` |
| onClick | 菜单项点击事件 | `Function()` | — | — |
| children | 子菜单结构信息 | `MenuItem[]` | — | — |


fork的项目，做了修改，由右键改成了左键点击出菜单。
