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
          title: "Home"
        },
        {
          id: 2,
          title: "TOS"
        },
        {
          id: 3,
          title: "About Us"
        },
        {
          id: 4,
          title: "Contact"
        },
      ]
    }
  }
}
</script>
<template>
  <listMenu :menuItems="data"/>
</template>