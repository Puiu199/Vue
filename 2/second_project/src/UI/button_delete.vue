<template>
    
    <button class="butt_delete">
        <slot>             
        </slot>
    </button>
</template>

<script>
export default {
    name:"button_delete"
}
</script>
<style scoped>
.butt_delete
{
    width: 100px;
    height: 35px;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    background-color: transparent;
    border: 1px solid red;
    text-transform: uppercase;
    font-weight: 700;
    letter-spacing: 1px;
    margin: 2px;
    text-shadow: -1px 0px  red;
    cursor: pointer;
}
    
</style>