<template>
  <v-layout
    id="one-time-donation"
    tag="section"
    mb-12
    wrap
  >
    <v-flex xs12>
      <doc-heading goto="one-time-donation">oneTime</doc-heading>
    </v-flex>

    <v-flex
      xs12
      my-2
      tag="v-divider"
    />

    <v-flex
      xs12
      mb-4
    >
      <doc-markdown>oneTimeBlurb</doc-markdown>
    </v-flex>

    <v-flex
      xs12
      text-center
    >
      <a
        aria-label="Support Vuetify through Paypal"
        href="https://paypal.me/vuetify"
        rel="noopener"
        target="_blank"
        title="Support Vuetify through Paypal"
      >
        <v-img
          alt="Paypal Logo"
          class="d-inline-block"
          src="https://cdn.vuetifyjs.com/images/social/paypal.png"
          width="150"
        />
      </a>
    </v-flex>
  </v-layout>
</template>
