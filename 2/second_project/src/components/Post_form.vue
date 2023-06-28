<template>
    <h4> Please insert youre data</h4>
    <form class="create_post" @submit.prevent>
        <input_form type="text" placeholder="Insert title" v-model="post.title" > </input_form><br>
        <input_form type="text" placeholder="Insert somtings" v-model="post.about" > </input_form><br>
        <div>
            <button-teal @click="create_post" required>Create</button-teal>     
            <button class="hide" @click="hide_dialog" required>X</button>  
         </div>
    </form>
</template>
<script>
export default {
    data(){
        return{
            post:{
                title:"",
                about:""
            }
        }
    },methods:{
        create_post(){
            this.post.id=Date.now(),
            this.$emit('create',this.post)
            this.post={
                title:'',
                about:''
            }
        },hide_dialog(){
            this.visibel_dialog=false;
        }
    }
}
</script>

<style scoped>
.create_post
{
    margin: 5px;
    display: grid;
    justify-items: center;
   
}
.hide
{
    text-transform: uppercase;
    font-size: 15px;
    font-weight: 700;
    border: none;
    text-shadow: 0.1px 0.1px .1px red;
    background-color: transparent;
    cursor: pointer;
}
form>div{
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border: none;

}
h4{
    text-transform:uppercase ;
}

</style>