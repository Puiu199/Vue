<template>  

<div v-if="posts.length>0">
    <Post_item class="post_list" v-for="post in posts" :post="post"
    :key="post.id" @remove="$emit('remove',post)"></Post_item>
</div>
<div v-else>
    <h2>
        <strong  class="strung_list">The list of posts is clear ^-^</strong>
    </h2>
</div>
</template>
<script>
import Post_item from "@/components/Post_item";
export default
{
    components:{Post_item},
    props:{
        posts:{
            type:Array,
            require:true
        }
    }
}
</script>

<style scoped>
.post_list
{  
    display: grid ;
    font-size: 15px;
    margin: auto;
    margin-top: 15px;
    margin-bottom: 15px;
}
.strung_list
{
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 15px;
}
*
{
    margin: 0%;
}
</style>