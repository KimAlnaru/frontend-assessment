<script setup>
    defineProps({
        data: {
            type: Object,
            required: true,
        }
    })
</script>

<template>
    <div class="container mb-5 w-100">
      <div class="forMobile">
        <div id="accordion">
            <div class="card" v-for="(item, index) in data" :key="item.title">
                <div class="card-header" :id="item.title + `id`">
                <h5 class="mb-0">
                    <button class="btn btn-link w-100" data-toggle="collapse" :data-target="`#` + item.title" :aria-expanded="item.title.includes('1')" :aria-controls="item.title">
                   {{ item.title }}
                    </button>
                </h5>
                </div>

                <div :id="item.title" :class="item.title.includes('1') ? 'collapse show' : 'collapse'" :aria-labelledby="item.title + `id`" data-parent="#accordion">
                <div class="card-body" v-html="item.content"></div>
                </div>
            </div>           
        </div>
      </div>
    </div>
</template>
<style scoped>

    .forMobile {
        display: block;
    }
    @media (min-width: 601px) {
        .forMobile {
            display: none;
        }
    }

    .btn {
        text-decoration: none;
        color: #000;
        font-weight: bold;
        text-align: left;
    }
</style>