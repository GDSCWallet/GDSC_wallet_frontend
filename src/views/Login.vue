<template>
  <v-sheet class="d-flex flex-column justify-center" style="height: 100%">
    <v-sheet class="d-flex justify-center">
      <v-card width="100%" max-width="500px">
        <v-card-title>Wallet</v-card-title>
        <v-card-actions>
          <v-row justify="end">
            <v-col cols="6">
              <v-btn
                href="https://wallet.ebg.tw/oauth/google/login"
                color="primary"
                block
              >
                <v-icon small left>mdi-google</v-icon>
                login
              </v-btn>
            </v-col>
          </v-row>
        </v-card-actions>
      </v-card>
    </v-sheet>
  </v-sheet>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Home",
  data() {
    return {};
  },
  mounted() {
    if (this.isLoggedin) return this.$router.push({ path: "/", replace: true });
  },
  methods: {},
  computed: {
    ...mapGetters({
      isLoggedin: "auth/isLoggedin",
    }),
  },
  watch: {
    isLoggedin() {
      if (this.isLoggedin)
        return this.$router.push({ path: "/", replace: true });
    },
  },
};
</script>