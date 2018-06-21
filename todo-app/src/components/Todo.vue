<template>
  <div class='ui centered card'>
    <b-card class="mb-2">
      <div class="content" v-show="!isEditing">
        <h2>
          {{todo.title}}
        </h2>
        <p class="card-text">
          {{ todo.project }}
        </p>
      </div>
      <div class="content" v-show="isEditing">
          <div class="form-group">
          <label for="todo-title" class="control-label">Title</label>
          <div class="">
            <input type="text" v-model="todo.title" class="form-control" id="todo-title" placeholder="Title">
          </div>
        </div>
        <div class="form-group">
          <label for="todo-project" class="control-label">Project</label>
          <div class="">
            <input type="text" v-model="todo.project" class="form-control" id="todo-project" placeholder="Password">
          </div>
          <div class="form-group">
            <button class='btn btn-success' v-on:click="hideForm">
              Close X
            </button>
          </div>
        </div>
      </div>
      <a href="#" class="btn btn-primary" v-on:click="showForm" v-show="!isEditing">Edit</a>
      <a href="#" class="btn btn-success" v-show="!isEditing && todo.done">Completed</a>
      <a href="#" class="btn btn-warning" v-show="!isEditing && !todo.done">Pending</a>
    </b-card>
</div>
</template>

<script type="text/javascript">
  export default {
    props: ['todo'],
    data () {
      return {
        isEditing: false
      };
    },
    methods: {
      showForm () {
        console.log(123);
        this.isEditing = true;
      },
      hideForm () {
        this.isEditing = false;
      }
    }
  };
</script>
