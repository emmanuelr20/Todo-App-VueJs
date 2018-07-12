<template>
    <div class="card">
        <div class="panel panel-default">
            <div class="panel-header">
                {{ todo.title }}
            </div>
            <div class="panel-body">
                {{ todo.description }}
            </div>
            <div class="panel-footer">
                <button class="btn btn-success" @click="completed" v-if="!todo.status"> Mark As Completed</button>
                <button class="btn btn-danger" @click="deleteTodo">Delete</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'todo-item',
    props: ['todo'],
    methods:{
        completed(){
            this.$store.dispatch('COMPLETE_TODO', this.todo);
        },
        deleteTodo(){
            this.$store.dispatch('DELETE_TODO',this.todo);
        }
    }
}
</script>

<style>

</style>
