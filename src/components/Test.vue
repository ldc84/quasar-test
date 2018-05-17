<template>
  <div class="test">
    <h5>Test Exemple</h5>
    <q-tabs class="shadow-2" align="justify" v-model="selTab" color="pink-5">
      <q-tab slot="title" name="tab1" icon="mail" label="Tab One" />
      <q-tab slot="title" name="tab2" icon="alarm" label="Tab Two" />
      <q-tab slot="title" name="tab3" icon="movie" label="Tab Three" />
      <q-tab-pane name="tab1">Tab One</q-tab-pane>
      <q-tab-pane name="tab2">Tab Two</q-tab-pane>
      <q-tab-pane name="tab3">Tab Three</q-tab-pane>
    </q-tabs>
    <div class="row bg-deep-purple-1">
      <div class="col-6">6</div>
      <div class="col-6">6</div>
    </div>
    <q-input placeholder="Text" v-model="text1" />
    <q-input placeholder="Text Label" stack-label="Stack Label" v-model="text2" />
    <q-select
      v-model="select"
      float-label="Is Quasar Awesome?"
     :options="selectOptions"
    />
    <q-datetime-range v-model="range1" class="full-width" />
    <q-toggle v-model="checked" label="Toggle Label" />
    <q-knob
      class="text-primary"
      v-model="knob"
      :min="0"
      :max="50"
    />
    <q-rating size="3rem" color="yellow" v-model="ratingModel" :min="0" :max="6" icon="star" />
    <q-dialog-select
      v-model="dialogSelect"
      :options="dialogSelectOptions"
    />
    <q-slider v-model="sliderStandard" :min="0" :max="50" />
    <q-btn loader icon="alarm" color="secondary" @click="simulateProgress">Button</q-btn>
    <q-btn
      loader
      :percentage="percentage"
      round
      color="primary"
      @click="startComputing"
      icon="cloud_upload"
    />
    <q-list style="max-width: 600px;">
      <q-item
        link
        v-for="(dialog, index) in types"
        :key="index"
        @click="dialog.handler()"
        v-ripple.mat
      >
        <q-item-side icon="settings" />
        <q-item-main :label="dialog.label" />
        <q-item-side right icon="keyboard_arrow_right" />
      </q-item>
    </q-list>
    agag <br>
    agag <br>
    agag <br>
    agag <br>
    agag <br>
    agag <br>
    agag <br>
    agag <br>
    agag <br>
    agag <br>
    agag <br>
    agag <br>
    agag <br>
    agag <br>
  </div>
</template>

<script>
import {QTabs, QTab, QTabPane, QOptionGroup, QInput, QSelect, QDatetimeRange, QToggle, QKnob, QRating, QDialogSelect, QSlider, QBtn, QIcon, ActionSheet, Toast, QList, QItem, QItemSide, QItemMain, Ripple} from 'quasar'

function showActionSheetWithIcons (gallery) {
  ActionSheet.create({
    title: 'Article Actions',
    gallery: gallery,
    actions: [
      {
        label: 'Delete',
        icon: 'delete',
        handler () {
          Toast.create('Deleted Article')
        }
      },
      {
        label: 'Share',
        icon: 'share',
        handler () {
          Toast.create('Shared!')
        }
      },
      {
        label: 'Play',
        icon: 'gamepad',
        handler () {
          Toast.create('Launched Game')
        }
      },
      {
        label: 'Favorite',
        icon: 'favorite',
        handler () {
          Toast.create('Added to favorites')
        }
      }
    ],
    dismiss: {
      label: 'Cancel',
      handler () {
        Toast.create('Cancelled...')
      }
    }
  })
}

export default {
  components: {QTabs, QTab, QTabPane, QOptionGroup, QInput, QSelect, QDatetimeRange, QToggle, QKnob, QRating, QDialogSelect, QSlider, QBtn, QIcon, QList, QItem, QItemSide, QItemMain},
  directives: {
    Ripple
  },
  data () {
    return {
      selTab: 'tab1',
      text1: '',
      text2: '',
      select: '',
      selectOptions: [
        {
          label: 'Google',
          value: 'goog'
        },
        {
          label: 'Facebook',
          value: 'fb'
        }
      ],
      range1: {
        from: null,
        to: null
      },
      checked: false,
      knob: 30,
      ratingModel: 4,
      dialogSelect: 'fb',
      dialogSelectOptions: [
        {
          label: 'Google',
          value: 'goog'
        },
        {
          label: 'Facebook',
          value: 'fb'
        },
        {
          label: 'Twitter',
          value: 'twtr'
        },
        {
          label: 'Apple Inc.',
          value: 'appl'
        },
        {
          label: 'Oracle',
          value: 'ora'
        }
      ],
      sliderStandard: 30,
      percentage: 0,
      interval: null,
      types: [
        {
          label: 'List with Icons',
          handler () {
            showActionSheetWithIcons()
          }
        },
        {
          label: 'Gallery with Icons',
          handler () {
            showActionSheetWithIcons(true)
          }
        },
        {
          label: 'List with Avatars',
          handler () {
            showActionSheetWithIcons()
          }
        },
        {
          label: 'Gallery with Avatars',
          handler () {
            showActionSheetWithIcons(true)
          }
        }
      ]
    }
  },
  methods: {
    simulateProgress (e, done) {
      // simulate a delay
      setTimeout(done, 3000)
    },
    startComputing (e, done) {
      this.percentage = 0
      this.interval = setInterval(() => {
        this.percentage += Math.floor(Math.random() * 8 + 10)
        if (this.percentage >= 100) {
          clearInterval(this.interval)
          done()
        }
      }, 700)
    }
  }
}
</script>

<style scoped>
  .test {padding:20px 15px;}
  h5 {margin-top:0;}
</style>
