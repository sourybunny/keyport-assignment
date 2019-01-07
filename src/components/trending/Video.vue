<template>
    <div class="videoItem">
        <div class= "image">
            <app-image :playbackId = "video.playbackId" :gifToken = "video.gifToken" :thumbnailToken= "video.thumbnailToken"></app-image>
            <app-duration :duration = "video.duration"></app-duration>
           
        </div>

        <div class="videoDetails">
            <app-channel-name :channel = "video.channelName"></app-channel-name>
            <app-title :title = "video.title"></app-title>   
            <div class="timeago-cost">
                <app-timeago :createdAt = "video.createdAt"></app-timeago>
                <app-cost :minutes = "video.duration/60" :costperminute = "video.costPerMinute" ></app-cost>
            </div>        
            
        </div>
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
        background-color: #fff;
        font-family: Arial,sans-serif;
        margin: 15px;
        text-align: left;
        width: 320px;
        max-width: 100%;
        border-top-left-radius: 6px;
        border-top-right-radius: 6px;
        box-shadow: -2px 1px 10px rgba(0, 0, 0, 0.15); 
}

.timeago-cost {
        display: flex;
        justify-content: space-between;
        align-items: baseline;
        margin: 0;
        color:gray;
        font-size: 0.9rem;
        
}

.videoDetails{
        padding: 0 5% 0 5%;
        font-family: 'Raleway';

}

</style>
