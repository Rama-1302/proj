<template>
    <div>
<h3> Component F username is : {{ username}}</h3>
    </div>
</template>

<script>
    export default {
         name: 'componentF',   
         inject:["username"]
    }
</script>

<style scoped>

</style>