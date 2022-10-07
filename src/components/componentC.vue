<template>
    <div>
   <h3> Component C</h3>
   <component-e/>
    </div>
</template>

<script>
import componentE from './componentE.vue'
    export default {
        name: 'componentC', 
        components:{
            componentE
        }  
    }
</script>

<style scoped>

</style>