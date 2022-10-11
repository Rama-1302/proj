<template>
    <div>
<h3 v-for=" name in list" :key="name.first">
   <slot :first="name.first" :last="name.last" >   </slot> </h3>
    </div>
</template>

<script>
    export default {
        name:'ListNames',
        data(){
            return {
                list:[
                    {
                        first:"Ramaprabha",last:"R"
                    },
                    {
                         first:"Vaishnavi",last:"V"
                    }

                ]
            }
        }
    }
</script>

<style scoped>

</style>