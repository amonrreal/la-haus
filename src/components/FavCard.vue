<template>
  <div class="fav-card bg-white my-3">
    <div
      v-if="gallery.length == 0"
      class="gallery empty rounded-lg cursor-pointer"
    >
      <img
        src="../assets/no-items.svg"
        alt="Empty"
        class="w-full object-cover rounded-lg"
      />
    </div>
    <div
      v-else-if="gallery.length <= 2"
      :class="
        gallery.length == 1
          ? 'gallery grid gallery_one rounded-lg cursor-pointer'
          : 'gallery grid gallery_two rounded-lg cursor-pointer'
      "
    >
      <img
        v-for="(img, index) in gallery"
        :key="index"
        :src="img.url"
        :alt="img.name"
        class="w-full object-cover rounded-lg"
      />
    </div>
    <div
      v-else
      class="gallery grid gallery_three relative bg-darkGreen opacity-100 rounded-lg cursor-pointer"
    >
      <img
        v-for="(img, index) in gallery.slice(0, 3)"
        :key="index"
        :src="img.url"
        :alt="img.name"
        class="w-full object-cover rounded-lg"
      />
      <div class="absolute flex w-full h-full justify-end items-center">
        <span class="text-white font-bold text-xl mr-5 z-30">
          + {{ gallery.length - 2 }}
        </span>
      </div>
    </div>
    <div class="fav-info mt-2">
      <p class="font-bold text-lg mb-2">{{ fav.attributes.name }}</p>
      <p class="font-light text-base text-gray-1">
        {{ properties.length }} propiedades guardadas
      </p>
    </div>
  </div>
</template>

<script>
import json from './data/real_estates.json'
export default {
  name: 'FavCard',

  props: {
    fav: { type: Object },
  },

  data() {
    return {
      properties: [],
      gallery: [],
    }
  },

  created() {
    this.getProperties(this.fav)
  },

  methods: {
    getProperties(property) {
      let _properties = []
      let _gallery = []

      const included = json.included
      const ids = property.attributes.real_estate_ids

      for (let i = 0; i < ids.length; i++) {
        const property_id = ids[i]
        let prop = included.find((p) => p.id == property_id)
        if (prop) {
          // console.log({ prop })
          _properties.push(prop)
        }
      }

      _gallery = _properties.reduce((acc, item) => {
        return [
          ...acc,
          { url: item.attributes.gallery_urls[0], name: item.name },
        ]
      }, [])

      // console.log({ _properties })
      this.properties = _properties
      // console.log({ _gallery })
      this.gallery = _gallery
    },
  },
}
</script>
