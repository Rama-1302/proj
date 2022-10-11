<template>
    <div>
 <h2 class="style"> Styles comp </h2>
 <slot> </slot>
    </div>
</template>

<script>
    export default {
        name:'StylesComp'
    }
</script>

<style scoped >
.style{
    color:green;
}
</style>