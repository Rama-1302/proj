<template>
    <div class="cards">
 <h2> hiii</h2>
 <slot></slot>


    <div>
       <slot name="heading"></slot>
    </div>
 
    <div>
      <slot name="foot" > </slot>
    </div>

    </div>
</template>

<script>
    export default {
        name:'CardComp',
        
    }
</script>

<style scoped>
.cards{
     border-width: 3px;
     border-style: double ;     
     width: 200px;}
</style>