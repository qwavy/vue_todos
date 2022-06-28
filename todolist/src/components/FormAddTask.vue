<template>
  <div>
    <!-- <input type="text" @input="onChange" :value="value"/> -->
    <input type="text" v-model="value"/>

    <button @click="onClick">add</button>
  </div>
</template>
<script>
export default {
  emits: ["onAdd"],
  data(){
    return{
      value: "",
    }
  },
  methods:{
    onChange(e){
      console.log(e);
      this.value = e.target.value
    },
    onClick(){
      this.$emit('onAdd',this.value)
      this.value = ""
    }
  }
}
</script>