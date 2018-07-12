<template>
    <div>
        <div v-if="todos">
            <todo-item v-for="(todo,index) in todos" :todo="todo" :key="index"></todo-item>
        </div>
    </div>
</template>

<script>
import TodoItem from "./todo-item.vue";
export default {
components:{TodoItem},
name: 'todo-list',
props: ['completed'],
computed :{
    todos(){
        if(this.completed === 'true'){
            return this.$store.getters.completed;
        }
        return this.$store.getters.incompleted;
    }
}

}
</script>

<style>

</style>
