<template>
  <ion-page class="ion-no-padding w-100">
    <ion-grid class="">
      <ion-row class="">
        <ion-col class="ion-text-center ion-no-padding ion-no-margin">
            <ion-img class="img" :src="logo"></ion-img>
        </ion-col>
      </ion-row>
      <ion-row>
          <ion-col class="bg-red">
              <ion-text>te</ion-text>
          </ion-col>
      </ion-row>
    </ion-grid>
  </ion-page>
</template>

<script>
// import router from "@/router";
import { IonGrid, IonRow, IonCol, IonText, IonPage, IonImg } from "@ionic/vue";
import { defineComponent, reactive, toRefs, onMounted } from "vue";

export default defineComponent({
  name: "Login",
  components: { IonGrid, IonRow, IonCol, IonText, IonPage, IonImg },
  setup() {
    const state = reactive({
      logo: "https://i.imgur.com/5FM7LmK.png",
    });

    onMounted(() => {
      console.log("Logn!");
    });
    return {
      ...toRefs(state),
    };
  },
});
</script>

<style lang="scss" scoped>
</style>
