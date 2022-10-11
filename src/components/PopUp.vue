<template>
    <div>
<h3> this a pop-up from the PopUp component</h3>
<input type="text" v-model=  " name1" />
<button @click=" $emit('close',name1)"> Close </button>
    </div>
</template>

<script>
    export default {
        name:"PopUp",

        emits:
    {
        close:(name1) => {
            if(!name1){
                return false
            }
            else{
                return true
            }

        },
    },
        data(){
            return {
                name1:'',
            }
        },
        

       
    }
</script>

<style scoped>

</style>
