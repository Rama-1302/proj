<template>
    <div>
    <h2 v-bind="$attrs"> The movie {{movie}} </h2>
    <h2> taken by {{budget}} crore budget is that worth watching ?? {{ Status ? 'Yes ':'No' }}</h2>
    </div>
</template>

<script>
    export default {
        name:'NewCom',
        props:{
            movie:{
                type: String,
                required: true,
                default:" default movie name "
                
            },
            budget:Number,
            Status:Boolean

        },
        inheritAttrs:false,
    }
</script>

<style scoped>

</style>