<template>
  <v-fab-transition>
    <v-btn
      v-show="top"
      v-scroll="onScroll"
      @click="toTop"
      fab
      dark
      fixed
      bottom
      right
      color="primary"
    >
      <v-icon>
        mdi-arrow-up
      </v-icon>
    </v-btn>
  </v-fab-transition>
</template>
<script>
  export default {
    data: () => ({ 
      top: false,
    }),

    methods: {
      onScroll (e) {
        if (typeof window === 'undefined') return
        const top = window.pageYOffset ||   e.target.scrollTop || 0
        this.top = top > 20
      },

      toTop () {
        this.$vuetify.goTo(0)
      }
    }
  }
</script>