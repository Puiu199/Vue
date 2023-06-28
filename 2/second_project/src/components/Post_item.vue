<template>
    <div class="post_item">
     <div class="info">
        <div class="ID"><strong>Id:</strong>{{post.id}}</div>
        <div class="title"><strong>Title :</strong>{{post.title}}</div>
        <div class="about"><strong>Body:</strong>{{ post.about}}</div>
    </div>
    <div>
        <button_delete @click="$emit('remove',post)">Delete</button_delete>
    </div>
    </div>
</template>
<script>
export default{
    props:{
        post:{
            type:Object,
            required:true,
        }
    }

}
</script>
<style scoped>
.post_item
{
    
    width: 50%;
    display: flex!important; ;
    border: 1px solid teal !important;
    justify-content: space-between;
    align-items: center;

}
.info
{
    border: none;
    display: grid;
    width: 100%;
    justify-content: left !important;;
}

.ID
{
    display: flex;
    align-items: center;
}
.title
{
    display: flex;
    justify-content: left;
    align-items: center;
    margin: 0%;
}
strong
{
    margin-left: 10px;
    margin-right: 15px;
}
.about
{
    display: flex;
    justify-content: left;
    align-items: center;
}
</style>