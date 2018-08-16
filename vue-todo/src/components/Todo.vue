<template>
<div id="todo">
  <div class="container todo-wrapper h-75 w-25">
    <div class="input-group mt-4">
      <input @keyup.enter="addTodo()" v-model="todoInput" type="text" class="form-control" placeholder="Add a Todo..." aria-label="Adding a Todo items" aria-describedby="basic-addon2">
      <div class="input-group-append">
        <button class="btn btn-vue" @click="addTodo()">Add</button>
      </div>
    </div>
    <p> </p>
    <hr>
    <div class="todo-list">
      <ul>
        <li v-for="(todoItem, i) in todoItems" :key="i" :id="'removePoint-'+i">
          <div class="todo">
            <label class="container">
              <input type="checkbox" v-model="todoItem.checked">
              <div class="checkmark"
                @click="todoItem.checked = !todoItem.checked">
              </div>
              <span :class="{'strike-through': todoItem.checked}">{{todoItem.item}} <a class="deleteTodo" v-if="todoItem.checked" @click="removeTodo(i)"></a></span>
            </label>
          </div>
          <hr>
        </li>
      </ul>
    </div>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      todoItems: [],
      todoInput: '',
    };
  },
  methods: {
    addTodo() {
      if (this.todoInput != '') {
        this.todoItems.push({
          item: this.todoInput,
          checked: false
        });
        this.todoInput = '';
      }
      return this.todoItems;
    },
    removeTodo(i) {
      this.todoItems.splice(i, 1);
    }
  },
}
</script>

<style lang="scss" scoped>
#todo {
    font-family: inherit;
    background-color: #35495e;
    height: 1000px;
    input[type='text'] {
        border: 1px solid black;
    }
    .todo-wrapper {
        box-shadow: -15px 20px 20px 20px;
        background-color: #dee2e6;
        border-radius: 10px;
        border: solid black 1px;
        .btn-vue {
            background-color: #42b883;
            border: solid black 1px;
        }
    }
    hr {
        color: #35495e;
        border: 0;
        width: 100%;
        background-color: #35495e;
        height: 1px;
    }
    .todo-list {
        display: block;
        position: relative;
        padding-left: 10px;
        margin-bottom: 12px;
        cursor: pointer;
        font-size: 22px;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
        ul {
            margin-left: -13%;
            li {
                .strike-through {
                    text-decoration: line-through;
                    opacity: 0.5;
                }
                .deleteTodo {
                    margin-top: 5px;
                    float: right;
                    cursor: pointer;
                    color: #000000;
                    border: 1px solid #000000;
                    border-radius: 0.25rem;
                    background: #42b883;
                    font-size: 20px;
                    display: inline-block;
                    line-height: 0;
                    padding: 13px 6px;
                }
                .deleteTodo:before {
                    content: "Del.";
                }
                list-style-type: none;
                .todo {
                    .container {
                        input[type='checkbox'] {
                            position: absolute;
                            opacity: 0;
                            cursor: pointer;
                        }
                        input[type='checkbox']:checked ~ .checkmark {
                            background-color: #42b883;
                        }
                        input:checked ~ .checkmark:after {
                            display: block;
                        }
                        .checkmark {
                            border: solid black 1px;
                            border-radius: 3px;
                            position: relative;
                            top: 6px;
                            left: 0;
                            height: 25px;
                            width: 25px;
                            display: inline-block;
                        }
                        .checkmark:after {
                            content: "";
                            position: absolute;
                            display: none;
                        }
                        .checkmark:after {
                            left: 9px;
                            top: 5px;
                            width: 5px;
                            height: 10px;
                            border: solid white;
                            border-width: 0 3px 3px 0;
                            -webkit-transform: rotate(45deg);
                            -ms-transform: rotate(45deg);
                            transform: rotate(45deg);
                        }
                    }
                }
            }
        }
    }
}
</style>
