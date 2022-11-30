<script setup>

defineProps({    
    text: {
        type:Object,
        required: true,
    }
})

</script>

<template>            
    <div class="d-flex flex-sm-row flex-column gap-3 justify-content-center" >
        <div class="card col-sm-3 col-12 shadow-sm" v-for="item in text" :key="item.text">             
            <div class="card-body d-flex flex-column"> 
                <img src="@/assets/images/400x300.png" alt="image" class="rounded w-100 pb-2"/>                                       
                <p class="card-text text-a text-center" v-html="item.text"></p>
                <div class="text-center mt-auto"><a href="#" class="btn btn-outline-dark rounded">READ MORE</a></div>                            
            </div>
        </div>        
    </div>  
                    
</template>

<style scoped>
.btn-outline-dark {
    border-radius: 100px !important;
    font-weight: bold;
    border: 2px solid;
}

.card:hover {
    transition: transform .2s;
    transform: scale(1.035);
    cursor: pointer;
}
</style>