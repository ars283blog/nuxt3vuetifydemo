<template>
  <div>
    <div class="d-flex align-center flex-column">
      <v-icon>mdi-home</v-icon>
      <v-card width="400">
        <v-card-title>This is a title</v-card-title>
        <v-card-subtitle>This is a subtitle</v-card-subtitle>
        <v-card-text> This is content </v-card-text>
      </v-card>
    </div>
      <div style="margin: 20px"><v-alert type="success">I'm a success alert.</v-alert>
      <br>
      <v-alert type="info">I'm an info alert.</v-alert>
      <br>
      <v-alert type="warning">I'm a warning alert.</v-alert>
      <br>
      <v-alert type="error">I'm an error alert.</v-alert>
    </div>
    
    <div class="text-center">
      <v-slider v-model="model" :max="rounded.length - 1" :tick-labels="rounded"></v-slider>

      <div class="py-3"></div>

      <v-sheet :class="radius" :max-width="model === 6 ? 128 : 256" class="mx-auto transition-swing secondary"
        elevation="12" height="128" width="100%"></v-sheet>

      <div class="py-3"></div>

      <code class="text-subtitle-1">.{{ radius }}</code>
    </div>

    <div>
    <v-slider
      v-model="slider1"
      color="orange"
      label="color"
    ></v-slider>

    <v-slider
      v-model="slider2"
      track-color="green"
      label="track-color"
    ></v-slider>

    <v-slider
      v-model="slider3"
      thumb-color="purple"
      label="thumb-color"
    ></v-slider>
  </div>
  <div>
    <div class="text-caption">Show ticks when using slider</div>

    <v-slider
      step="10"
      show-ticks
    ></v-slider>

    <div class="text-caption">Always show ticks</div>

    <v-slider
      step="10"
      show-ticks="always"
    ></v-slider>

    <div class="text-caption">Tick size</div>

    <v-slider
      step="10"
      show-ticks="always"
      tick-size="4"
    ></v-slider>

    <div class="text-caption">Tick labels</div>

    <v-slider
      :ticks="tickLabels"
      :max="3"
      step="1"
      show-ticks="always"
      tick-size="4"
    ></v-slider>
  </div>
  </div>
</template>
<script>
export default {
  data: () => ({
    model: 3,
    slider1: 0,
      slider2: 50,
      slider3: 100,
      tickLabels: {
          0: 'Figs',
          1: 'Lemon',
          2: 'Pear',
          3: 'Apple',
        },
    rounded: [
      '0',
      'sm',
      'md',
      'lg',
      'xl',
      'pill',
      'circle',
    ],
  }),

  computed: {
    radius() {
      let rounded = 'rounded'
      const value = this.rounded[this.model]

      if (value !== 'md') {
        rounded += `-${value}`
      }

      return rounded
    },
  },
}
</script>