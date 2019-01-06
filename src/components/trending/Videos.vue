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
        margin: 2% auto;
        justify-content: center;
        flex-wrap:wrap;
        

    }
</style>
