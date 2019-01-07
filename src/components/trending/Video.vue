<template>
    <div class="videoItem">
      
        <app-image :playbackId = "video.playbackId" :gifToken = "video.gifToken" :thumbnailToken= "video.thumbnailToken"></app-image>
        <app-title :title = "video.title"></app-title>
        <app-channel-name :channel = "video.channelName"></app-channel-name>
        <app-duration :duration = "video.duration"></app-duration> 
        <app-cost :minutes = "video.duration/60" :costperminute = "video.costPerMinute" ></app-cost>
        <app-timeago :createdAt = "video.createdAt"></app-timeago>
    </div>
</template>

<script>

import Title from './details/Title.vue';
import ChannelName from './details/ChannelName.vue';
import Duration from './details/Duration.vue';
import Cost from './details/Cost.vue';
import Timeago from './details/Timeago.vue';
import Image from './details/Image.vue';

export default {

    props: ['video'],
    components: {
        'appTitle': Title,
        'appChannelName': ChannelName,
        'appDuration': Duration,
        'appCost': Cost,
        'appTimeago': Timeago,
        'appImage': Image
    }
}
</script>

<style>

.videoItem {
    margin: 2%;
    width: 20%;
    text-align: center;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.15);
}
.videoItem img {
    width:100%;
    height: 260px;
}
</style>
