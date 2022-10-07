<template>
    <div>
<h3> Component E</h3>
<component-f/>
    </div>
</template>

<script>
import componentF from './componentF.vue'
    export default {

         name: 'componentE',   
         components: { componentF },
        
    }
</script>

<style scoped>

</style>