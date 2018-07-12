<template>
    <div class="container">
      <h1> Todo Application <small> (Using Vuex)</small></h1>
      <form @submit="createTodo">
        <label for="">Title</label>
        <input v-model="title"  type="text" class="form-control" required>
        <label for="">Description</label>
        <textarea rows="2" v-model="description" class="form-control" required></textarea>
        <br>
        <button class="btn btn-success" type="submit"> Submit</button>
      </form>
      <br>
      <hr>
      <div class="row">
        <div class="col-md-6">
          <h4>Completed Todo</h4>
          <todo-list completed=true></todo-list>
        </div>
        <div class="col-md-6">
          <h4>Pending Todo</h4>
          <todo-list completed=false></todo-list>
        </div>
      </div>
    </div>
</template>

<script>
import TodoList from "./components/todo-list.vue";
export default {

name: 'app',
components :{TodoList},
data(){
  return {
    title: '',
    description: ''
  }
},
methods:{
  createTodo(e){
    e.preventDefault();
    this.$store.dispatch('ADD_TODO',this);
    this.title=this.description ="";
  }
}
}
</script>

<style>

</style>
