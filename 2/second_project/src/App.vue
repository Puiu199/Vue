<template>
    <div class="app">
        
       <div class="titel_app">
        <strong class="strong">List of posts</strong><br>
        <button-teal @submit.prevent @click="show_dialog">Create</button-teal>
        <win_dialog  v-model:show="visibel_dialog">
            <Post_form @create="createPost"></Post_form>
        </win_dialog>
     </div>
     <button @click="get_post">show</button>
        <div class="list_post" v-if="!ispostLoading">
            <Post_list :posts="posts" @remove="remove_Post" ></Post_list>
            <my-select v-model="select_option" :options="sortOptions"></my-select>
        </div>
        <div v-else>
            <div>Whaiting . . .</div>
        </div>
    </div>
</template>
<script>
import Post_form from "@/components/Post_form";
import Post_list from "@/components/Post_list";
import axios from "axios";

export default{
components:{
    Post_form,Post_list
},
    data(){
        return{
            posts:[],
            visibel_dialog:false,
            ispostLoading:false,
            select_option:'',
            sortOptions:[{value:"title", name:"Sort by title"},{value:"body",name:"Sort by body"}]
        }
    },methods:{
        createPost(post){

            this.posts.push(post);
            this.visibel_dialog=false;
        },
        remove_Post(post)
        {
            this.posts=this.posts.filter(p=> p.id !==post.id)}
        ,show_dialog(){
           
            this.visibel_dialog=true;
        },async get_post()
        {
            try {
                this.ispostLoading=true;
                setTimeout( async ()=>{
                const response= await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10')
                for(let i=0;i<response.data.length;i++){
                this.posts.push(response.data[i])
                }
                console.log(this.posts);
                this.ispostLoading=false;
             },1000)
                
                
            } catch(e) {
                console.warn(Error+"^_^")
                
            }
            finally{                               
            }
        }

    },mounted(){
        this.get_post();
    },watch:{select_option(newValue){console.log(newValue)}

    },
}
</script>
<style scoped>
.app{
    margin-top: 5px;
    width: 100%;
    display: grid;    
    border: 1px solid black;
}
.titel_app
{
    display: grid;
    justify-items: center;
    padding: 15px;
}
.list_post
{
    display: grid;
}
*{
    margin: 0%;
    border: 1px solid black!important;;
}
.strong
{
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 24px;
    text-transform: uppercase;
    margin-top: 15px;
    text-decoration: solid;
    width: 250px;
    height: 80px;
}


</style>