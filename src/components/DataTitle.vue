<template>
    <div class="title-area">
        <div class="country-name">{{ text }}</div>
        <div class="date-time">
            {{ timestamp }}
        </div>
    </div>
    
</template>

<script>
import moment from 'moment';

export default {
    name: 'DataTitle',
    props: ['text', 'dataDate'],
    computed: {
        timestamp: function() {
            return moment(this.dataDate).format('MMMM Do YYYY, h:mm:ss a');
        }
    }
}
</script>

<style>

.title-area {
    padding: 15px;
}

.country-name {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 30px;
    font-weight: bold;
    padding: 10px;
}

.date-time {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 24px;
}

</style>
