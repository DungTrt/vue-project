<template lang="">
    <div class="alert-container">
        <h2>Success!</h2>
        <slot></slot>
    </div>
</template>
<script>
export default {
    
}
</script>
<style scoped>
    .alert-container{
        position: absolute;
        top:50;
        right:50;
        width:200px;
        color: #666;
        border: 1px solid teal;
        border-radius: 4px;
        padding: 20px;
        background-color: #f8f8f8;
        
    }    
</style>