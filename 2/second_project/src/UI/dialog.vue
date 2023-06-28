<template>
    <div class="dialog" v-if="show" @click.stop="hideDialog">
        <div @click.stop class="widContente">
            <slot> </slot>
        </div>
    </div>
</template>

<script>
    export default {
        name :"win_dialog",
        props:{
            show:{
                type:Boolean,
                default:true
            }
        },methods: {
            hideDialog(){
                this.$emit('update:show',false)
            }
        }
    }
</script>

<style scoped>
.dialog{
    width:100%;
    height: 100%;
    position: absolute;
    background-color: rgba(0,0, 0, 0.5);
    display: flex;
}
.widContente
{
    margin:auto ;
    background-color: white;
    border-radius: 15px;
    display: grid;
    width: 50%;
    height: 300px;
    padding: 25px;
    border: 1px solid black;
    justify-items: center;
     overflow: hidden;
}
</style>