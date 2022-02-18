<template>
  <div
    class="list grid sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 mt-5"
  >
    <FavCard v-for="(item, index) in data" :key="index" :fav="item" />
    <div class="fav-card bg-white my-3">
      <div
        class="add flex justify-center items-center rounded-lg cursor-pointer"
      >
        <fa icon="plus" class="text-primary text-2xl" />
      </div>
      <div class="fav-info text-center mt-2">
        <p class="font-bold text-lg mb-2 text-primary">Crear una nueva lista</p>
      </div>
    </div>
  </div>
</template>

<script>
import FavCard from './FavCard'
export default {
  name: 'List',

  components: { FavCard },

  props: {
    data: { type: Array },
  },
}
</script>

<style lang="scss">
.list {
  .fav-card {
    .gallery {
      min-height: 220px;
      img {
        border: 1px solid #e5f0ee;
        height: 220px;
      }
    }
    .gallery_two {
      grid-template-columns: 45% 10% 45%;
      img:nth-child(1) {
        grid-column: 1/3;
        grid-row: 1;
        z-index: 10;
      }
      img:nth-child(2) {
        grid-column: 2/4;
        grid-row: 1;
      }
    }
    .gallery_three {
      grid-template-columns: 20%;
      img:nth-child(1) {
        grid-column: 1/3;
        grid-row: 1;
        z-index: 10;
      }
      img:nth-child(2) {
        grid-column: 2/4;
        grid-row: 1;
        z-index: 5;
      }
      img:nth-child(3) {
        grid-column: 3/5;
        grid-row: 1;
        z-index: 1;
        opacity: 0.3;
      }
    }
    .add {
      min-height: 220px;
      background-color: #ebedff;
    }
  }
}
</style>
