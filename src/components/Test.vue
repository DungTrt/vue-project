<template lang="">
    <p>Using text interpolation: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span> {{count}}</p>
    <button type="button" @click="inCrease">InCrease</button>
    <span v-if="Object.keys(employeeSelected).length > 0">{{employeeSelected.name}}</span>
</template>
<script>

export default {
    props:{
        employeeSelected:{
            type: Object,
        }
    },
    data() {
        return {
            rawHtml:`<span style="color: red">This should be red.</span>`,
            count:0
        }
    },
    methods: {
        inCrease(){
            this.count++;
        }
    },
}
</script>
<style lang="">
    
</style>