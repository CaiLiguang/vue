<template>
  <div id="app">
    <span v-bind:title="message">
      鼠标悬停几秒钟查看此处动态绑定的提示信息！
    </span>
    <ul>
        <li v-for="item in items" v-bind:class="{finished : item.isFinished}">
          {{item.lable}}
        </li>
    </ul>
    <p v-if="seen">现在你看到我了</p>
  </div>
</template>

<script>
export default {
  data : function (){
    return {
      message : '页面加载于 ' + new Date().toLocaleString(),
      items : [
        {
            lable : '吃早饭',
            isFinished : true
        },
        {
            lable : '晨练',
            isFinished : false
        }
      ],
      liClass : 'this is liClass',
      seen : false
    }
  }
}
</script>

<style>
.finished {
  text-decoration : underline;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
