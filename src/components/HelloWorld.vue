<template>
  <v-container>
    <v-row class="text-center">
      <v-col
        class="mb-5"
        cols="12"
      >
        <h2 class="headline font-weight-bold mb-3">
          各種申請
        </h2>

        <v-row justify="center">
          <v-col class="mx-1" v-for="(next, i) in shinsei" :key="i" >
            <dialog-vue :button-name="next.text" />
          </v-col>
        </v-row>
      </v-col>

      <v-col
        class="mb-5"
        cols="12"
      >
        <h2 class="headline font-weight-bold mb-3">
          清算
        </h2>

        <v-row justify="center">
          <dialog-vue v-for="(link, i) in seisan"
            :key="i" :button-name="link.text"></dialog-vue>
        </v-row>
      </v-col>

    </v-row>
  </v-container>
</template>

<script>
import DialogVue from './DialogVue';

  export default {
    name: 'HelloWorld',

    components: {
      DialogVue
    },

    data: () => ({
      seisan: [
        {
          text: '清算',
          href: 'https://vuetifyjs.com',
        },
      ],
      shinsei: [
        {
          text: '残業申請',
          href: 'https://vuetifyjs.com/components/api-explorer',
        },
        {
          text: '遅刻申請',
          href: 'https://vuetifyjs.com/layout/pre-defined',
        },
        {
          text: '休暇申請',
          href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
        },
        {
          text: '有給申請',
          href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
        },
        {
          text: '出張申請',
          href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
        },
      ],
    }),
  }
</script>
