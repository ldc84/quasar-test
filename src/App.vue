<template>
  <!-- Don't drop "q-app" class -->
  <div id="q-app">

    <q-layout
      ref="layout"
      view="lHh Lpr fff"
      :left-class="{'bg-grey-2': true}"
    >
      <q-toolbar slot="header" class="glossy" ref="header">
        <q-scroll-observable @scroll="userHasScrolled" />
        <q-btn
          flat
          @click="$refs.layout.toggleLeft()"
        >
          <q-icon name="menu" />
        </q-btn>

        <q-toolbar-title>
          Quasar App Test
          <div slot="subtitle">Running on Quasar v{{$q.version}}</div>
        </q-toolbar-title>
      </q-toolbar>

      <div slot="left">
        <SideMenu />
      </div>

      <router-view />

      <div slot="footer" class="glossy">
        <q-toolbar-title>
          Footer
        </q-toolbar-title>
      </div>
    </q-layout>
  </div>
</template>

<script>
import SideMenu from './components/layout/SideMenu'
import {
  QLayout,
  QToolbar,
  QToolbarTitle,
  QBtn,
  QIcon,
  QList,
  QListHeader,
  QScrollObservable
} from 'quasar'

export default {
  name: 'index',
  data () {
    return {}
  },
  components: {
    QLayout,
    QToolbar,
    QToolbarTitle,
    QBtn,
    QIcon,
    QList,
    QListHeader,
    QScrollObservable,
    SideMenu
  },
  methods: {
    userHasScrolled (scroll) {
      if (scroll.direction === 'down' && scroll.position >= 100) {
        this.$refs.header.classList.add('active')
      }
      else {
        this.$refs.header.classList.remove('active')
      }
      // console.log(scroll)
      // {
      //   position: 56, // pixels from top
      //   direction: 'down', // 'down' or 'up'
      //   directionChanged: false, // has direction changed since this handler was called?
      //   inflexionPosition: 56 // last scroll position where user changed scroll direction
      // }
    }
  }
}
</script>

<style>
  .layout-footer .glossy {
    height:50px;
    padding:0.6rem;
    color:#fff;
    background-color:#0273d4;
    box-sizing:border-box;
  }
  .layout-header {
    box-shadow:none;
  }
  header .glossy {
    top:0;
    box-shadow:0 2px 4px -1px rgba(0,0,0,0.2),
              0 4px 5px rgba(0,0,0,0.14),
              0 1px 10px rgba(0,0,0,0.12);
    transition:.3s all ease-in-out;
  }
  header .active {
    top:-80px;
  }
</style>
