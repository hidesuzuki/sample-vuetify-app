<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/logo.svg')"
          class="my-3"
          contain
          height="200"
        />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          Welcome to Vuetify
        </h1>

        <p class="subheading font-weight-regular">
          For help and collaboration with other Vuetify developers,
          <br>please join our online
          <a
            href="https://community.vuetifyjs.com"
            target="_blank"
          >Discord Community</a>
        </p>
      </v-col>

      <v-col
        class="mb-5"
        cols="12"
      >
        <h2 class="headline font-weight-bold mb-3">
          各種申請
        </h2>

        <v-row justify="center">
          <a
            v-for="(next, i) in shinsei"
            :key="i"
            :href="next.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ next.text }}
          </a>
          <dialog-vue v-for="(next, i) in shinsei"
            :key="i" :button-name="next.text" class="subheading mx-3"></dialog-vue>
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

      <v-col
        class="mb-5"
        cols="12"
      >
        <v-row justify="center">
          <dialog-vue :button-name="'buttonを押せ'"></dialog-vue>
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

    // methods:{
    //   dialogClose() {
    //     this.dialog = false;
    //   }
    // },

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
      // dialog: false,
    }),
  }
</script>
