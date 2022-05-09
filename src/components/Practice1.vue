<template lang="">
    <fieldset>
        <legend>Practice1</legend>
        <div>
            <input type="text" v-model="number"/>
            <span :class="changeClass">{{parseInt(number)|| 'Error'}}</span>
        </div>
    </fieldset>
    
</template>
<script>
export default {
    data(){
        return {
            number:'',
        }
    },
    computed: {
        changeClass(){
            var value=parseInt(this.number);
            if(value){
                if(value<10){
                    return 'white'
                }
                else if(9<value && value<20){
                    return 'yellow'
                }
                else{
                    return 'red';
                }
            }
            return ''; 
        }
    }
}
</script>
<style scoped>
    .white{
        color:white;
    }
    .yellow{
        color:yellow;
    }
    .red{
        color:red;
    }
</style>