<script setup >
 import {ref,reactive } from 'vue';
 const todoState =reactive({
    todo: '',
    invalid:null,
    errMsg:''
 }); 

 const emit = defineEmits(['create-todo']);

const createTodo = () => {
todoState.invalid=null;
    if(todoState.todo !== "") {
        emit('create-todo', todoState.todo);
        todoState.todo="";
        return;
    }

    todoState.invalid = true;
    todoState.errMsg = "Todo can't be empty";


}


</script>
<template>
    <div class="input-wrap">
        <input type="text" v-model="todoState.todo" />
        <button @click="createTodo()"> Create </button>
    </div>
    <p v-show="todoState.invalid" class="err -msg">{{ todoState.errMsg }}</p>
</template>
<style lang="scss" scoped>
    .input-wrap{
        display:flex;
        transition: 250ms ease;
        border: 2px solid #00c680;
        &:focus-within{
            box-shadow:  0 -4px 6px -1px rgb(0 0 0 / 0.1), 0 -2px 4px -2px rgb(0 0 0 / 0.1);
        }
        input{
            width: 100%;
            padding: 8px 6px;
            border: none;
            &:focus{
                outline: none;
            }
        }
        button{
            padding: 8px 16px;
            border: none;
        }
    }
</style>