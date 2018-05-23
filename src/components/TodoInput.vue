<template>
    <div>
        <input type="text" v-model="newTodoItem">
        <button v-on:click="addTodo">add</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newTodoItem : ''
        }
    },

    methods:{
        addTodo() {
            if(this.newTodoItem !== ''){
                var tmp = this.newTodoItem && this.newTodoItem.trim();
                localStorage.setItem(tmp, tmp);
                this.clearInput();
            }else{
                alert("input text!");
            }
        },
        clearInput(){
            this.newTodoItem = '';
        }
    }
}
</script>

