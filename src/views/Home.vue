<template>
  <div class="home h-full">
    <div class="container my-5">
      <div class="row">
        <div class="col-md-12 text-center">
          <h1 class="font-bold text-title">
            Listas de favoritos
          </h1>
        </div>
        <div class="col-md-12 col-lg-10 m-auto">
          <List :data="list.data" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import List from '../components/List'
import json from '../components/data/real_estates.json'
export default {
  name: 'Home',

  components: { List },

  data() {
    return {}
  },

  created() {
    console.log(json)
  },

  computed: {
    list() {
      return json
    },
  },
}
</script>

<style lang="scss"></style>
