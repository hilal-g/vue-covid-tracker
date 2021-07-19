<template>
  <header>
    <div class="title-font">
      Covid-19 Tracker
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style>

header {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 30px;
  background-image: linear-gradient(to right, #9F1717, #E61A00);
  color: #FFF;
}

.title-font {
  font-size: 40px;
  font-weight: bold;
}

</style>
