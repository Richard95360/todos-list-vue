<template>
  <form @submit.prevent="addTechno">
      <label for="techno">Techno à ajouter</label>
      <br>
      <input type="text" name="techno" v-model="techToLearm">
      <br>
      <button type="submit">ajouter</button>
  </form>
</template>

<script>
import { ref } from '@vue/reactivity';
export default {
  setup(props, ctx){
      let techToLearm = ref("");

    const addTechno = function(){
       console.log("Form | addTechno() | techToLearm.value", techToLearm.value);
       ctx.emit("add", techToLearm.value);
       techToLearm.value = '';
    }
    return{ techToLearm, addTechno}
  }
}
</script>

<style>

</style>