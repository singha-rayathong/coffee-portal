<template>
  <v-app dark>
    <v-app-bar
      absolute
      dark
      shrink-on-scroll
      prominent
      src="/puau-cover.jpeg"
      fade-img-on-scroll
      height="120"
    >
      <template v-slot:extension>
        <v-tabs centered background-color="brown darken-1">
          <v-tab>เมนู</v-tab>
          <v-tab>คำสั่งซื้อ</v-tab>
        </v-tabs>
      </template>
    </v-app-bar>

    <v-main style="margin-top: 220px">
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light> mdi-repeat </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-apps",
          title: "Welcome",
          to: "/",
        },
        {
          icon: "mdi-chart-bubble",
          title: "Inspire",
          to: "/inspire",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "ปู่อู๋ คอฟฟี่",
    };
  },
};
</script>
