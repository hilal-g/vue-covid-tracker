<template>
    <div class="main-div">
        
        <!-- BOX 1 -->
        <div class="box-1">
            <h3 class="box-title">
                Cases
            </h3>

            <div class="box-font">
                <span class="info-title">Active: </span>
                {{ numberWithCommas(stats.slice(-1)[0].Active) }}
            </div>

            <div class="box-font">
                <span class="info-title">Total: </span>
                {{ numberWithCommas(stats.slice(-1)[0].Confirmed) }}
            </div>
        </div>

        <!-- BOX 2 -->
        <div class="box-2">
            <h3 class="box-title">
                Survival Rates
            </h3>

            <div class="box-font">
                <span class="info-title">Total Deaths: </span>
                {{ numberWithCommas(stats.slice(-1)[0].Deaths) }}
            </div>

            <div class="box-font">
                <span class="info-title">Total Recovery: </span>
                {{ numberWithCommas(stats.slice(-1)[0].Recovered) }}
            </div>
        </div>
        
    </div>
</template>

<script>

export default {
    name: 'DataBoxes',
    props: ['stats'],
    methods: {
        numberWithCommas(x) {
            return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
        }
    }
}
</script>

<style>

.main-div {
    display: flex;
    justify-content: center;
    align-items: center;
}

.box-1 {
    display: inline-block;
    background-color: #ffc9ab;
    padding: 15px;
    border-radius: 10px;
    width: 550px;
    margin-right: 5px;
}

.box-2 {
    display: inline-block;
    background-color: #ffb084;
    padding: 15px;
    border-radius: 10px;
    width: 550px;
    margin-left: 5px;
}

.box-title {
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: bold;
    font-size: 24px;
    padding: 5px;
}

.info-title {
    font-weight: bold;
    padding: 5px;
}

.box-font {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
}

</style>
