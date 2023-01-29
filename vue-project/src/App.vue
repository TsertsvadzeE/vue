<script>

export default {
  data() {
    return{
      length: null,
      width: null,
      height:null,
      color: null,
      show: false
    }
  },
  computed: {
    calculateSpace(){
      return this.width * this.height
    },
    calculateMoculoba(){
      return this.calculateSpace * this.length
    }
  }
}
</script>

<template>
  <div>
    <form>
      <label>Length</label><br>
      <input v-model="length"/><br/>

      <label>Width</label><br>
      <input v-model="width"/><br/>

      <label>Height</label><br>
      <input v-model="height"/><br/>

      <input type="color" v-model="color"/><br/>
    </form>
    <br>
    <button @click.prevent="show = ! show">
      <span v-if="!show">Show</span>
      <span v-if="show">Hide</span>
    </button>
    <p v-if="show">ფართობი: {{calculateSpace }}</p>
    <p v-if="show">მოცულობა: {{ calculateMoculoba}}</p>
  </div>
  <br>
  <div :style="{height: height + 'px', width: width + 'px', border: '1px solid black', backgroundColor:color }">
  </div>
</template>