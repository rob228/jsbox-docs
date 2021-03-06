# type: "text"

`text` 用于创建一个可多行编辑的文本框，目前不支持富文本（但支持 HTML)：

```js
{
  type: "text",
  props: {
    text: "Hello, World!\n\nThis is a demo for Text View in JSBox extension!\n\nCurrently we don't support attributed string in iOS.\n\nYou can try html! Looks pretty cool."
  },
  layout: $layout.fill
}
```

将会在画布上显示一大段话，并且可以编辑。

# props

属性 | 类型 | 读写 | 说明
---|---|---|---
type | $kbType | 读写 | 键盘类型
darkKeyboard | boolean | 读写 | 是否黑色键盘
text | string | 读写 | 文本内容
html | string | 只写 | 通过 html 渲染富文本
font | $font | 读写 | 字体
textColor | $color | 读写 | 文本颜色
align | $align | 读写 | 对齐方式
placeholder | string | 读写 | placeholder
selectedRange | $range | 读写 | 选中区域
editable | boolean | 读写 | 是否可编辑
selectable | boolean | 读写 | 是否可选择
insets | $insets | 读写 | 边距

# focus()

获取焦点，弹出键盘。

# blur()

模糊焦点，收起键盘。

# events: didBeginEditing

`didBeginEditing` 在开始编辑后回调：

```js
didBeginEditing: function(sender) {

}
```

# events: didEndEditing

`didEndEditing` 在结束编辑后回调：

```js
didEndEditing: function(sender) {
  
}
```

# events: didChange

`didChange` 在内容变化时回调：

```js
didChange: function(sender) {

}
```

# events: didChangeSelection

`didChangeSelection` 在选择区域变化时回调：

```js
didChangeSelection: function(sender) {

}
```

同时，`text` 继承自 `scroll`，所以 scroll 支持的全部事件和属性 text 也一样支持。

# 自定义键盘工具栏

通过这样的方式自定义键盘工具栏：

```js
$ui.render({
  views: [
    {
      type: "input",
      props: {
        accessoryView: {
          type: "view",
          props: {
            height: 44
          },
          views: [

          ]
        }
      }
    }
  ]
});
```

# 自定义键盘视图

通过这样的方式自定义键盘视图：

```js
$ui.render({
  views: [
    {
      type: "input",
      props: {
        keyboardView: {
          type: "view",
          props: {
            height: 267
          },
          views: [

          ]
        }
      }
    }
  ]
});
```