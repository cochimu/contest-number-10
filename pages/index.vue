<template lang="pug">
v-row(justify="center" align="center")
  v-col(cols="12" sm="8" md="6")
    v-card(class="logo py-4 d-flex justify-center")
      nuxt-logo
      vuetify-logo
    v-card
      v-card-title(class="headline")
        welcome to the Vuetify + Nuxt.js template
      v-card-text
        p Vuetify is a progressive Material Design component framework for Vue.js. It was designed to empower developers to create amazing applications.
        p For more information on Vuetify, check out the
          a(
            href="https://vuetifyjs.com"
            target="_blank"
            rel="noopener noreferrer"
          )
          a documentation
        p If you have questions, please join the official
          a(
            href="https://chat.vuetifyjs.com/"
            target="_blank"
            rel="noopener noreferrer"
            title="chat"
          ) discord
        p Find a bug? Report it on the github
          a(
            href="https://github.com/vuetifyjs/vuetify/issues"
            target="_blank"
            rel="noopener noreferrer"
            title="contribute"
          ) issue board
        p Thank you for developing with Vuetify and I look forward to bringing more exciting features in the future.
        div(class="text-xs-right")
          em
            small &mdash; John Leider
        hr(class="my-3")
        a(
          href="https://nuxtjs.org/"
          target="_blank"
          rel="noopener noreferrer"
        ) Nuxt Documentation
        br
        a(
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          rel="noopener noreferrer"
        ) Nuxt GitHub
      v-card-actions
        v-spacer
        v-btn(
          color="primary"
          nuxt
          to="/inspire"
        ) Continue
</template>
