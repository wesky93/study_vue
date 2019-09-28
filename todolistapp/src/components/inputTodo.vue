<template>
  <div>
    <input type="text" class="input" id="task" placeholder="입력 후 엔터!" v-model.trim="todo" @keyup.enter="addTodo">
    <span class="addbutton" @click="addTodo">추 가</span>
  </div>
</template>
<script type="text/javascript">
  import eventBus from "./EventBus.vue";
    export default {
        name: "inputTodo",
        data(){
            return {todo:""}
        },
        methods:{
            addTodo(){
                eventBus.$emit('add-todo',this.todo)
                this.todo = ''
            }
        }
    }
</script>

<style>
  * {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
  }

  .input {
    border: none;
    width: 75%;
    height: 35px;
    padding: 10px;
    float: left;
    font-size: 16px;
  }

  .addbutton {
    padding: 10px;
    width: 25%;
    height: 35px;
    background: #d9d9d9;
    color: #555555;
    float: left;
    text-align: center;
    font-size: 13px;
    cursor: pointer;
    -webkit-transition: 0.3s;
    -moz-transition: 0.3s;
    -ms-transition: 0.3s;
    -o-transition: 0.3s;
    transition: 0.3s;
  }

  .addbutton:hover {
    background-color: #bbbbbb;
  }
</style>

