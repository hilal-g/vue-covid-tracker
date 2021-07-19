<template>
  <main v-if="!loading">
    <DataTitle :dataDate="dataDate" :text="title" />
    <DataBoxes :stats="stats" />
  </main>

  <main v-else>
    <div class="fetch-text">
      Fetching Data 
    </div>
    <div class="fetch-image">
      <img :src="loadingImage" alt="" />
    </div>
  </main>
</template>

<script>

import DataTitle from '@/components/DataTitle';
import DataBoxes from '@/components/DataBoxes';

export default {
  name: 'Home',
  components: {
    DataTitle,
    DataBoxes,
  },
  data() {
    return {
      loading: true,
      title: 'Italy',
      dataDate: '',
      status: {},
      countries: [],
      loadingImage: require('../assets/hourglass.gif'),
    }
  },
  methods: {
    async fetchCovidData() {
      const res = await fetch('https://api.covid19api.com/dayone/country/italy');
      const data = await res.json();
      return data;
    },
  },
  async created() {
    const data = await this.fetchCovidData();
    
    this.dataDate = data.Date;
    this.stats = data;
    this.loading = false;
  },
};
</script>

<style>

* {
  font-family: sans-serif;
  margin: 0;
}

.fetch-text {
  display: flex;
  justify-content: center;
  align-items: center;
  color: gray;
  font-size: 24px;
  padding: 15px;
}

.fetch-image {
  display: flex;
  justify-content: center;
  align-items: center;
}

</style>
