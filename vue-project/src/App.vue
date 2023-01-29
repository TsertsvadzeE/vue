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
          url: "http://google.com"
        },
        {
          id: 2,
          title: "TOS",
          url: "http://google.com"
        },
        {
          id: 3,
          title: "About Us",
          url: "http://google.com"
        },
        {
          id: 4,
          title: "Contact",
          url: "http://google.com"
        },
      ]
    }
  }
}
</script>
<template>
  <listMenu :menuItems="data"/>
</template>