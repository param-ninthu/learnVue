<script setup >
 import {ref , reactive} from 'vue';
 const todo =ref("Boom"); 

 console.log(todo); 

 const todoState = reactive({
    todo:"Reactive todo"
 })

 console.log(todoState); 
 

</script>
<template>
    <div class="input-wrap">
        <input type="text" v-model="todoState.todo" />
        <button> Create </button>
    </div>
    <p> {{ todoState.todo }} </p>
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