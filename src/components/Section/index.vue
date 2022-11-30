<script setup>
   import json from '../../data.json'; 
   import Tab from './Tab.vue';
   import Accordion from './Accordion.vue'; 
</script>

<template>    
    <Tab :data="json" />
    <Accordion :data="json" />
</template>