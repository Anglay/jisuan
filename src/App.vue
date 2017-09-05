<template>
  <div id="app">
    <Calculator></Calculator>
  </div>
</template>

<script>
import Calculator from "@/components/Calculator"
export default {
  name: 'app',
  components: { Calculator }
}
</script>

<style>
* {
  /*-webkit-user-select: none; /*禁止用户进行复制、选择*/
  box-sizing: border-box;
  /*设置元素的内边距和边框包括在总宽高内进行绘制计算*/
  outline: 0;
  /*移除当元素被点击后或获取到焦点时候出现的焦点虚线-轮廓线*/
  -webkit-tap-highlight-color: transparent;
  /*移除点击后出现的灰色背景*/
}

input {
  -webkit-user-select: text !important;
}

body {
  line-height: 1;
  /*行高默认1倍*/
}


/*移除默认下划线并且背景颜色设置为透明*/

a,
a:visited {
  text-decoration: none;
  background-color: transparent;
}


/*/美化滚动条*/

a,
img {
  border: none;
}



/*移除默认的边框*/

input,
fieldset {
  padding: 0;
}

a,
a:visited,
a:hover,
a:focus,
a:active {
  color: inherit;
}

input {
  line-height: normal;
}

p,
figure,
dl,
dd,
input,
button,
input,
optgroup,
select,
textarea {
  margin: 0;
}

ul {
  margin-top: 0;
  margin-bottom: 0;
  padding-left: 0;
  padding-right: 0;
  list-style-type: none;
}

select {
  font: inherit;
  font-size: inherit;
  color: inherit;
}


/*字体风格*/

body {
  font-family: '微软雅黑', 'Helvetica Neue', Helvetica, 'Microsoft Yahei', 'Hiragino Sans GB', 'WenQuanYi Micro Hei', sans-serif;
}

html,
body {
  width: 100%;
  height: 100%;
  margin: 0 auto;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background: #f0f0f0;
  width: 320px;
  height: 420px;
  margin: 15px auto;
  text-align: center;
  padding: 10px;
  border-radius: 10px;
  overflow: hidden;
}
</style>
