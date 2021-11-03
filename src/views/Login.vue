<template>
  <ion-page class="">
    <ion-row>
      <ion-col class="ion-text-center">
        <ion-img class="img" :src="logo"></ion-img>
      </ion-col>
    </ion-row>
    <ion-row class="b-rt-md bg-primary ion-item-justify-center ion-margin-vertical h-md ion-text-center">
      <ion-col v-if="!isReset">
        <ion-text class="cursor-pointer">
          <h3 @click="swithLogin" :class="isLogin === true ? 'text-white' : 'opacity-30-white'">Login</h3>
        </ion-text>
      </ion-col>
      <ion-col v-if="!isReset">
        <ion-text class="cursor-pointer">
          <h3 :class="!isLogin ? 'text-white' : 'opacity-30-white'" @click="swithRegister">Register</h3>
        </ion-text>
      </ion-col>
      
      <ion-col v-if="isReset">
        <ion-text>
          <h3 class="text-white">Forgot password</h3>
        </ion-text>
      </ion-col>
    </ion-row>
    <ion-row class="b-rt-md mt-min-md ion-item-justify-center bg-white h-md">
      <ion-col class="mx">
        <ion-item class="mt-md" v-if="isLogin === false">
          <ion-label position="stacked">Name *</ion-label>
          <ion-input inputmode="text" type="text" clear-input></ion-input>
        </ion-item>

        <ion-item class="mt-md">
          <ion-label position="stacked">Email *</ion-label>
          <ion-input inputmode="email" type="email" clear-input></ion-input>
        </ion-item>

        <ion-item class="mt-md">
          <ion-label position="stacked">Password *</ion-label>
          <ion-input inputmode="password" type="password" clear-input></ion-input>
        </ion-item>

        <div class="mt-md">
          <ion-text class="cursor-pointer" @click="swithReset" color="primary">Forgot password?</ion-text>
        </div>

        <div class="mt-md">
          <ion-button expand="block" mode="ios" class="border-radius-sm" color="primary">{{ isLogin == true ? 'Login' : 'Register' }}</ion-button>
        </div>

        <div class="mt-md">
          <ion-button expand="block" fill="clear" class="ion-text-capitalize border-radius-sm" color="primary">{{ isLogin == true ? 'Create New Account' : 'Login' }}</ion-button>
        </div>
      </ion-col>
    </ion-row>
  </ion-page>
</template>

<script>
// import router from "@/router";
import { IonRow, IonCol, IonText, IonPage, IonImg, IonInput, IonButton, IonItem, IonLabel } from "@ionic/vue";
import { defineComponent, reactive, toRefs } from "vue";

export default defineComponent({
  name: "Login",
  components: { IonRow, IonCol, IonText, IonPage, IonImg, IonInput, IonButton, IonItem, IonLabel },
  setup() {
    const state = reactive({
      logo: "https://i.imgur.com/5FM7LmK.png",
      isLogin: true,
      isReset: false
    });

    const swithRegister = () => {
      state.isLogin = false
    }

    const swithLogin = () => {
      state.isLogin = true
    }

    const swithReset = () => {
      state.isReset = true
    }

    return {
      ...toRefs(state),
      swithRegister,
      swithLogin,
      swithReset
    };
  },
});
</script>

<style lang="scss" scoped>
</style>
