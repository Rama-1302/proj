<template>
<div>    
<h2> Hii from RamaPrabha.vue component for {{name}} who belong to {{ place}}</h2>

</div>
</template>

<script>
    export default {        
    
        name: 'RamaPrabha',   
        props: ["name","place"],
        

        
    };
</script>

<style scoped>

</style>