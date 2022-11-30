<script setup>

    defineProps({
        data: {
            type: Object,
            required: true,
        }
    })    
    
</script>
<template>   
    <div class="container mb-5 mt-5 pt-5 pb-5 w-75">
        <div class="forDesktop">
            <ul class="nav nav-tabs" id="myTab" role="tablist">
                <li class="nav-item" v-for="(item, index) in data" :key="item">
                    <a :class="item.title.includes('1') ? 'active nav-link' : 'nav-link'" 
                    :id="item.title" data-toggle="tab" :href="`#` + index" role="tab" :aria-controls="item.title" :aria-selected="item.title.includes('1') ? true : false">{{ item.title }}</a>
                </li>           
            </ul>
            <div class="tab-content m-3" id="myTabContent">
                <div v-for="(item, index) in data" :key="index" :class="item.title.includes('1') ? 'tab-pane fade show active' : 'tab-pane fade'" 
                :id="index" role="tabpanel" :aria-labelledby="item.title" v-html="item.content"></div>
            </div>
        </div>      
    </div>   
</template>

<style scoped>

    .forDesktop {
        display: none;
    }
    @media (min-width: 601px) {
        .forDesktop {
            display: block;
        }
    }

    .nav-link {
        color: #3f3f3f;
    }
    .active {
        font-weight: bold;
    }
</style>