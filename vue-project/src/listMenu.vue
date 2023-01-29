<script>
export default{
    props:{
        menuItems: {type:Array, required:true}
    },
    data(){
        return{
           show: true 
        }
    },
    methods: {
        eventHandler: function(e){
            console.log(e.target.innerHTML, e.target.getAttribute('href'))
        },
        showHendler: function(){
            this.$data.show =! this.$data.show
        }
    },
}
</script>
<template>
    <ul>
        <li v-for="item in menuItems" :key="item.id">
            <a :href="item.url" @click.prevent="eventHandler">{{ item.title }}</a>
        </li>
    </ul>
    <br />
    <button @click.prevent="showHendler">
        <span v-if="show">Hide</span>
        <span v-if="!show">Show</span>
    </button>
    <p v-if="show">Paragraph</p>
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