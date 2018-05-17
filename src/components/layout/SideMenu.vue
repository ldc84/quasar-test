<template>
  <div class="sidemenu">
    <q-list no-border link inset-delimiter>
      <q-list-header class="bg-blue-6">
        <q-side-link item to="/">Side Menu</q-side-link>
      </q-list-header>
      <q-side-link item to="/Test">
        <q-item-side icon="pets" />
        <q-item-main label="TestComponent" />
      </q-side-link>
      <q-side-link item to="/Card">
        <q-item-side icon="picture_in_picture_alt" />
        <q-item-main label="Card" />
      </q-side-link>
      <q-side-link item to="/Collapsible">
        <q-item-side icon="list" />
        <q-item-main label="Collapsible" />
      </q-side-link>
      <q-side-link item to="/Carousel">
        <q-item-side icon="view_carousel" />
        <q-item-main label="Carousel" />
      </q-side-link>
      <q-side-link item to="/Gallery">
        <q-item-side icon="photo" />
        <q-item-main label="Gallery" />
      </q-side-link>
    </q-list>
  </div>
</template>

<script>
import {
  QList,
  QItem,
  QListHeader,
  QSideLink,
  QItemSide,
  QItemMain
} from 'quasar'

export default {
  components: {
    QList,
    QItem,
    QListHeader,
    QSideLink,
    QItemSide,
    QItemMain
  },
  data () {
    return {}
  }
}
</script>

<style scoped>
  .q-list {padding-top:0;}
  .q-list-header {color:#fff; font-size:20px; line-height:34px;}
  .q-list-header .q-item.router-link-active {background:none;}
</style>
