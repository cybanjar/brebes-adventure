<template>
  <ion-page>
    <ion-content>
      <ion-grid class="ion-no-padding">
        <ion-row
          class="ion-justify-content-center ion-align-items-center h-100"
        >
          <ion-col class="ion-text-center">
            <ion-text color="light">
              <h3>Not Found!</h3>
            </ion-text>
            <router-link to="/">
              <ion-text color="light">
                <p class="text-light">Home</p>
              </ion-text>
            </router-link>
          </ion-col>
        </ion-row>
      </ion-grid>
    </ion-content>
  </ion-page>
</template>

<script>
// import router from "@/router";
import { IonGrid, IonRow, IonCol, IonText, IonPage } from "@ionic/vue";
import { defineComponent, reactive, toRefs } from "vue";

export default defineComponent({
  name: "Splash",
  components: { IonGrid, IonRow, IonCol, IonText, IonPage },
  setup() {
    const state = reactive({});

    return {
      ...toRefs(state),
    };
  },
});
</script>

<style lang="scss" scoped>
.h-100 {
  height: 100vh;
}

.text-light {
  font-weight: 300;
}

ion-page {
  --ion-background-color: #bbd1bd;
}

ion-content {
  --background: var(
    --ion-color-primary
  ); // Replace this with color of your choice
}
</style>
