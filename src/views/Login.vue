<template>
  <ion-page class="w-100">
    <ion-row>
      <ion-col class="ion-text-center">
        <ion-img class="img" :src="logo"></ion-img>
      </ion-col>
    </ion-row>
    <ion-row class="b-rt-md bg-primary ion-item-justify-center h-md ion-text-center">
      <ion-col>
        <ion-text color="light cursor-pointer">
          <h3 @click="swithLogin">Login</h3>
        </ion-text>
      </ion-col>
      <ion-col>
        <ion-text class="cursor-pointer">
          <h3 class="opacity-30-white" @click="swithRegister">Register</h3>
        </ion-text>
      </ion-col>
    </ion-row>
    <ion-row class="b-rt-md mt-min-md bg-white ion-item-justify-center h-md ion-text-center">
      <ion-col>
        <ion-text color="dark">
          <h3>{{ isLogin == true ? 'Login' : 'Register'}}</h3>
        </ion-text>
      </ion-col>
    </ion-row>
  </ion-page>
</template>

<script>
// import router from "@/router";
import { IonRow, IonCol, IonText, IonPage, IonImg } from "@ionic/vue";
import { defineComponent, reactive, toRefs } from "vue";

export default defineComponent({
  name: "Login",
  components: { IonRow, IonCol, IonText, IonPage, IonImg },
  setup() {
    const state = reactive({
      logo: "https://i.imgur.com/5FM7LmK.png",
      isLogin: true
    });

    const swithRegister = () => {
      state.isLogin = false
    }

    const swithLogin = () => {
      state.isLogin = true
    }

    return {
      ...toRefs(state),
      swithRegister,
      swithLogin,
    };
  },
});
</script>

<style lang="scss" scoped>
</style>
