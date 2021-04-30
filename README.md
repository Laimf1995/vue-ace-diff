# vue-ace-diff
在 [vue-ace-diffy](https://github.com/svilenkov/vue-ace-diffy) 基础上新增属性

添加了 editable，copyLinkEnabled相关属性

# Install

- `npm i --save git+https://git@github.com/laimeifeng/vue-ace-diff.git`

# Getting started

Include the Ace Diff stylesheet, or use your own.

`.acediffy__container` CSS class wraps the AceDiff editor. You need to set an explicit width and height, as well as the `position: relative`

Create a new component and **extend** it with the `AceDiffy` module.

```vue
<template>
  <div id="ace-diffy"></div>
</template>

<script>
  import AceDiffy from 'vue-ace-diffy'

  export default {
    extends: AceDiffy,
    data() {
      // Default options
      return {
        leftContent: '', // Left pane diff text content
        rightContent: '', // Right pane diff text content
        editorId: 'ace-diffy', // AceDiffy element ID
        leftEditable: null, // Left pane diff text editable
        leftCopyLinkEnabled: null, // Left pane diff text copy
        rightEditable: null, // right pane diff text editable
        rightCopyLinkEnabled: null // right pane diff text copy
      }
    },
    mounted () {
      require('brace/ext/language_tools') // important prerequisite for syntax highlighting
      require('brace/mode/json') // change this to any syntax (mode) that will be set
      require('brace/theme/github') // change if you want to use a different theme

      // Initialize a new Ace Diff editor
      this.createEditor({
        mode: 'ace/mode/json',
        theme: 'ace/theme/github'
      })
    }
  }
</script>

<style>
@import '~ace-diffy/dist/ace-diffy-light.css';

.acediff__container {
  width: 700px;
  height: 200px;
  margin: 2rem auto;
  position: relative;
}
</style>
```

# Development

To manually test the diff editor in a browser at run the following:

```bash
npm run serve
```
