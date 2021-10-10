<template>
  <ion-page>
    <ion-grid class="ion-no-padding">
      <ion-row class="ion-justify-content-center ion-align-items-center h-100">
        <ion-col class="ion-text-center">
          <ion-img class="img" :src="logo"></ion-img>
          <ion-text color="primary">
            <h1>
              Brebes <span class="text-light">Adventure</span>
              <ion-text color="secondary">.</ion-text>
            </h1>
          </ion-text>
          <ion-text color="primary text-light"
            >Location object platform
          </ion-text>
        </ion-col>
      </ion-row>
    </ion-grid>
  </ion-page>
</template>

<script>
import router from "@/router";
import { IonGrid, IonRow, IonCol, IonText, IonImg, IonPage } from "@ionic/vue";
import { defineComponent, reactive, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "Splash",
  components: { IonGrid, IonRow, IonCol, IonText, IonImg, IonPage },
  setup() {
    const state = reactive({
      logo: "https://i.imgur.com/Tm95oZX.png",
    });

    onMounted(() => {
      setTimeout(() => {
        router.replace({ path: "login" });
      }, 2000);
    // console.log(router);
    });
    return {
      ...toRefs(state),
    };
  },
});
</script>

<style lang="scss" scoped>
.red {
  background-color: red;
}

.img {
  height: 48px;
  width: 48px;
  margin: auto;
}

.h-100 {
  height: 100vh;
}

h1 {
  font-size: 24px;
  font-weight: 800;
}

.text-light {
  font-weight: 300;
}
</style>
