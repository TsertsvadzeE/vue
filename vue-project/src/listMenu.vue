<script>
export default{
    props:{
        menuItems: {type:Array, required:true}
    }
}
</script>
<template>
    <ul>
        <li v-for="item in menuItems" :key="item.id">{{ item.title }}</li>
    </ul>
</template>
<style scoped>
ul {
    display: flex;
}
ul li{
    list-style: none;
    margin-right: 25px;
}
</style>