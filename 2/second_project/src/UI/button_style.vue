<template>
    <button class="but">
    <slot></slot>
</button>
</template>
<script>
export default{
    name:"button-teal"
}
</script>
<style scoped>
.but{

    width: 100px;
    height: 35px;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    background-color: transparent;
    border: 1px solid teal;
    text-transform: uppercase;
    font-weight: 700;
    letter-spacing: 1px;
    cursor: pointer;
}
</style>