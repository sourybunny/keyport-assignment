<template>
   
        <p>Posted <em>{{moment(getTime()).fromNow()}}</em></p>
    
</template>

<script>
var moment = require('moment');
export default {
    data(){
        return {
            moment: moment
        }
    },
    props: ['createdAt'],
    methods: {
        getTime(){
            return this.createdAt;
        }
    }
}
</script>