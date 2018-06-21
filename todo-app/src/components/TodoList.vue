<template>
  <div>
  <b-container>
    <b-row>
        <b-col>Todo A</b-col>
        <b-col>Todo B</b-col>
        <b-col>Todo C</b-col>
    </b-row>
    <b-row>
      <b-list-group>
        <b-list-group-item>
          <b-button variant="success">
            Completed Tasks <b-badge variant="light">{{todos.filter(todo => {return todo.done === true}).length}}</b-badge>
          </b-button>
        </b-list-group-item>
        <b-list-group-item>
          <b-button variant="success">
            Pending Tasks <b-badge variant="light">{{todos.filter(todo => {return todo.done === false}).length}}</b-badge>
          </b-button>
        </b-list-group-item>
      </b-list-group>
    </b-row>
    <b-row>
      <todo v-for="todo in todos" v-bind:todo="todo" :key="todo.id"></todo>
    </b-row>
  </b-container>
  </div>
</template>

<script type = "text/javascript" >
import Todo from './Todo'
export default {
  props: ['todos'],
  components: {
    Todo
  }
};
</script>
<style>
</style>
