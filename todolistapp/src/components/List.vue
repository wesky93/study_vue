<template>
  <ul id="todolist">
    <li v-for="(a,index) in todolist" :class="checked(a.done)" @click="doneToggle(index)">
      <span>{{a.todo}}</span>
      <span v-if="a.done"> (완료)</span>
      <span class="close" @click.stop="deleteTodo(index)">&#x00D7;</span>
    </li>
  </ul>
</template>
<script type="text/javascript">
    import eventBus from "./EventBus.vue";

    export default {
        created() {
            eventBus.$on('add-todo', this.addTodo);
        },
        data() {
            return {
                todolist: [
                    {todo: "영화보기", done: false},
                    {todo: "주말 산책", done: true},
                    {todo: "ES6 학습", done: false},
                    {todo: "잠실 야구장", done: false},
                ]
            }
        },
        methods: {
            checked(done) {
                if (done) return {checked: true};
                else return {checked: false};
            },
            addTodo(todo) {
                if (todo !== "") {
                    this.todolist.push({todo: todo, done: false});
                }
            },
            doneToggle(index) {
                this.todolist[index].done = !this.todolist[index].done;
            },
            deleteTodo(index){
                this.todolist.splice(index,1);
            }
        },
    }
</script>

<style>
  ul {
    margin: 0;
    padding: 0;
  }

  ul li {
    cursor: pointer;
    position: relative;
    padding: 8px 8px 8px 40px;
    background: #eeeeee;
    font-size: 14px;
    -webkit-transition: 0.2s;
    -moz-transition: 0.2s;
    -ms-transition: 0.2s;
    -o-transition: 0.2s;
    transition: 0.2s;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }

  ul li:hover {
    background: #ddd;
  }

  ul li.checked::before {
    content: "";
    position: absolute;
    border-color: #ffffff;
    border-style: solid;
    border-width: 0px 1px 1px 0px;
    top: 10px;
    left: 15px;
    transform: rotate(45deg);
    height: 8px;
    width: 8px;
  }

  .close {
    position: absolute;
    right: 0;
    top: 0;
    padding: 12px 16px 12px 16px
  }

  .close:hover {
    background-color: #f44336;
    color: white;
  }
</style>
