<script>
export default{
    props:{
        menuItems: {type:Array, required:true}
    },
    data(){
        return{
           description: ""
        }
    },
    methods: {
        eventHandler: function(e){
            console.log(e.target.innerHTML, e.target.getAttribute('href'))
            this.description = e.target.getAttribute('des')
        }
    },
}
</script>
<template>
    <ul>
        <li v-for="item in menuItems" :key="item.id">
            <a :href="item.url" :des="item.description" @click.prevent="eventHandler">{{ item.title }}</a>
        </li>
    </ul>
    <br />
    <div>{{ description }}</div>
</template>
<style scoped>
ul {
    list-style-type: none;
}
ul li{
    float: left;
    margin-left: 20px;
}
</style> 