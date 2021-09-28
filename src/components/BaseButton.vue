<template>
<div>
  <button id="actif">actif</button>
  <button :disabled="inactive" id="inactif">inactif</button>

  <button :style="bdanger">danger</button>
  <button :style="bwarn">warn</button>
  <button :style="bprimary">primary</button>

  <button :style="bprimary" @click="handleClick">handleClick</button>

</div>
</template>

<script>
export default {
  name: "BaseButton",
  props:{
    colorPalette:{
      type:Object,
    },
    handleClick:{
      type:Function,
    }
  },
  data(){
    return{
      inactive:true
    }
  },
  computed:{
    bdanger() {
      return 'background-color:'+this.colorPalette.danger.bg;
    },
    bwarn() {
      return 'background-color:'+this.colorPalette.warn.bg;
    },
    bprimary() {
      return 'background-color:'+this.colorPalette.primary.bg;
    }
  }
}
</script>

<style scoped>
#actif:hover{
  opacity: 0.33;
}

button{
  width: 200px;
  height: 30px;
  margin-left: 15px;
  border-radius: 25px;
  background-color: #3CB371;
  color: midnightblue;
}

</style>