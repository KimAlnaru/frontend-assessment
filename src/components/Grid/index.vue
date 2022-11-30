<script setup>
    import Cards from './Cards.vue';   
    import Text from '../../text.json'    
</script>

<template>        
    <div class="container mt-5 mb-5">      
        <Cards :text="Text"/>         
    </div>       
</template>