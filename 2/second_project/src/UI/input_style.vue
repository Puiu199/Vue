<template>    
    <input type="text" :value="modelValue" @input="updateInput" class="input">
    <slot></slot>

</template>

<script>
    export default {
        name:"input_form",
        props:{
            modelValue:[String,Number]
        },methods:{
            updateInput(event)
            {
                this.$emit('update:modelValue',event.target.value)
            }
        }
    }
</script>

<style scoped>
.input
{
    margin-top: 15px;
    text-transform: uppercase;
    width:300px;
    border: none;
    border-bottom: 2px solid teal;
    text-align: center;
}

</style>