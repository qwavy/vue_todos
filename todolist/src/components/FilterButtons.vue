<template>  
    <button @click="onAll">all</button>
</template>
<script>
export default {
    emits:['onFilter'],
    props:['']
    methods:{
        onAll(){
            console.log('al')
        }
    }
}
</script>