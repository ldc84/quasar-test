<template>
  <div class="carousel layout-padding">
    <q-carousel arrows dots fullscreen class="text-white">
      <div slot="slide" class="bg-primary">
        <div>Slide 1</div>
      </div>
      <div slot="slide" class="bg-secondary">
        Slide 2
      </div>
      <div slot="slide" class="bg-tertiary">
        Slide 3
      </div>
    </q-carousel>
  </div>
</template>

<script>
import {
  QCarousel,
  QIcon,
  QModal
} from 'quasar'

export default {
  components: {
    QCarousel,
    QIcon,
    QModal
  },
  data () {
    return {}
  }
}
</script>

<style scoped>
  
</style>
