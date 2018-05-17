<template>
  <div class="gallery layout-padding">
    <p class="caption">Gallery</p>
    <q-gallery :src="gallery" />

    <p class="caption">Gallery Carousel</p>
    <q-gallery-carousel
      :src="gallery"
    />
  </div>
</template>

<script>
import {
  QGallery,
  QGalleryCarousel
} from 'quasar'

export default {
  components: {
    QGallery,
    QGalleryCarousel
  },
  data () {
    return {
      gallery: [
        'statics/parallax1.jpg',
        'statics/parallax2.jpg'
      ]
    }
  }
}
</script>

<style scoped>

</style>
