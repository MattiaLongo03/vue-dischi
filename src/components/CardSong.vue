<template>
  <div class="col">
    <div class="cards">
      <img
        :src="imgUrl"
        :alt="name"
        class="img-fluid"
      >
      <h2 class="titolo">
        {{ name }}
      </h2>
      <div class="info">
        <span class="author">
          {{ author }}
        </span>
        <span class="year">
          {{ year }}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardSong',
  props: {
    imgUrl: String,
    name: String,
    author: String,
    year: String,
  },
};
</script>

<style lang="scss" scoped>
.cards {
  margin: 20px;
  padding: 20px;
  height: 325px;
  background-color: #2E3A46;
  border-radius: 10px;
}

.titolo {
  margin-top: 10px;
  color: white;
  font-size: 20px;
  text-align: center;
}

.info {
  display: flex;
  flex-direction: column;
  text-align: center;
  color: gray;
}
</style>
