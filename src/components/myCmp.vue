<template>
    <div>
      {{hello}}
      <br>
      文本插值:<span v-html="mustaches_pf"></span>var<span v-html="mustaches_sf"></span>
      <br>
      一次性插值:{{cmd_once_pf}}<span v-html="cmd_once"></span>{{cmd_once_sf}}
      <br>
      html解析指令: {{cmd_html_pf}}<span v-html="rawHtml"></span>{{cmd_html_sf}}
      <br>
      属性绑定指令: {{cmd_bind_pf}}<span v-html="dynamicId"></span>{{cmd_bind_sf}}
      <br>
      属性绑定指令简写方式: {{cmd_bind_pf}}<span v-html="dynamicId_simple"></span>{{cmd_bind_sf}}
      <br>
      数据绑定语法 和 属性绑定 可以 使用表达式:
      <br>
      {{isShow ? exp + '拼接后缀':'miss'}}
      <br>

    </div>
</template>

<script>
    export default {
        name: "myCmp",
        data(){
          return{
            hello:'hello cmp',
            //文本插值:
            mustaches_pf:"<span style=\"color: red\">{{</span>",
            mustaches_sf:"<span style=\"color: red\">}}</span>",
            //一次性 指令
            cmd_once_pf: '<span ',
            cmd_once_sf: '>{{var}}</span>',
            cmd_once:"<span style=\"color: red\">v-once</span>",
            //html解析指令:
            cmd_html_pf: '<span ',
            cmd_html_sf: '="rawHtml"></span>',
            rawHtml:"<span style=\"color: red\">v-html</span>",
            //属性绑定指令:
            cmd_bind_pf: '<span ',
            cmd_bind_sf: '="dynamicId"></span>',
            dynamicId:"<span style=\"color: red\">v-bind:id</span>",
            //属性绑定指令简写方式:
            dynamicId_simple:"<span style=\"color: red\">:id</span>",
            //数据绑定语法 和 属性绑定 可以 使用表达式
            isShow:true,
            exp:"{{ number + 1 }}" +
              "{{ ok ? 'YES' : 'NO' }}" +
              "{{ message.split('').reverse().join('') }}" +
              "<div v-bind:id=\" 'list-' + id\"></div>",

          }
        }
    }
</script>

<style scoped>

</style>
