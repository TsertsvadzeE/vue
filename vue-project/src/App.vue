<script>
import listMenu from './listMenu.vue';
export default{
  components:{
    listMenu
  },
  data(){
    return{
      data: [
        {
          id: 1,
          title: "Home",
          url: "http://google.com",
          description: "Some Big Description 1"
        },
        {
          id: 2,
          title: "TOS",
          url: "http://google.com",
          description: "Some Big Description 2"
        },
        {
          id: 3,
          title: "About Us",
          url: "http://google.com",
          description: "Some Big Description 3"
        },
        {
          id: 4,
          title: "Contact",
          url: "http://google.com",
          description: "Some Big Description 4"
        },
      ]
    }
  }
}
</script>
<template>
  <listMenu :menuItems="data"/>
</template>