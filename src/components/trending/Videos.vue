<template>
    <div class="videoList">
        <app-video v-for = "video in videos" :video="video">
            

        </app-video>
    </div>
</template>

<script>
import Video from './Video.vue';
export default {
    props: ['videos'],
    components: {
        'appVideo': Video
    },
    methods: {
       
    }

}
</script>

<style>
    .videoList {
            display: flex;
            flex-wrap: wrap;
            align-items: flex-start;
            justify-content: center;
            margin: 0;
            text-align: center;  
    }
</style>
