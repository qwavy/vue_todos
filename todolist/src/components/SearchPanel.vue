<template>
<div>
    <!-- <new-title/> -->
    <input :value="modelValue" placeholder="type to search" @input="$emit('onSeacrh',)"/>
</div>
</template>

<script>
export default {
    emits:['onSearch'],
    props:["modelValue"],
    methods:{
        onInput(e){
            console.log(e)
            this.$emit('update:modelValue',e.target.value)
        }
    }
}
</script>