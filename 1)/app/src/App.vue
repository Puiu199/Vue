<template>
    <form @submit.prevent>
        <input type="text" @input="input_title=$event.target.value" v-bind:value="title"><br>
        <input type="text" @input="input_body=$event.target.value" v-bind:value="body"><br>
        <button class="add"  @click="add_post">Click +1</button>
    </form>
    
    <div class="post" v-for="post in posts">
        <div><strong>Id:</strong>{{ post.id}}</div>
        <div><strong>Title :</strong> {{ post.title}}</div>
        <div><strong>About :</strong> {{ post.about}}</div>
  </div>
 
</template>
<script>
export default {
    data()
    {
        return{
            number:0,
            posts:[
                {id:"1",title:"Post Number 1",about:"I create post number 1"},
                {id:"2",title:"Post Number 2",about:"I create post number 2"},
                {id:"3",title:"Post Number 3",about:"I create post number 3"}
            ],
            title:"",
            body:""
        }
    },methods:{
        
        add_post()
        {
            const newPost=
            {
                id:Date.now(),
                title:this.input_title,
                about:this.input_body
            };
            this.posts.push(newPost); 
            this.input_title="";
            this.input_body=" ";   
        }
        

    }
}
</script>
<style>

*{
    margin: 5px;
}
button
{
    
    width: auto;
    height: auto;
}
strong{
    color: black!important;
}
form
{
    margin: 10px;
    display: grid;
    justify-content: center;
    align-items: centere;
}
.post{
    margin-top: 15px;
    width: 100%;
    height: 80px;
    display: grid;
    align-items: center;
    justify-items: left;

    border: 1px solid teal;
    color: grey;
}
.add{
    border: 1px solid teal;
    color: blueviolet;
    width: auto;
    background-color: transparent;
    text-transform: uppercase;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
