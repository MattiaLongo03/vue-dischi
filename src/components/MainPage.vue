<template>
  <div class="content">
    <div class="container">
      <div
        v-if="arrDisc"
        class="row row-cols-5"
      >
        <CardSong
          v-for="disc in arrDisc"
          :key="disc.poster"
          :img-url="disc.poster"
          :name="disc.title"
          :author="disc.author"
          :year="disc.year"
        />
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import CardSong from '@/components/CardSong.vue';

export default {
  components: {
    CardSong,
  },
  data() {
    return {
      arrDisc: null,
      urlApi: 'https://flynn.boolean.careers/exercises/api/array/music',
    };
  },
  created() {
    axios.get(this.urlApi)
      .then((axiosResponse) => {
        console.log(axiosResponse);
        this.arrDisc = axiosResponse.data.response;
      });
  },
};
</script>

<style lang="scss" scoped>
  .content{
    width: 100%;
    height: 937px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #1E2D3B;
  }
</style>
