<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 1</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header>

      <ExploreContainer name="Tab 1 page" />

      <ion-button id="open-modal" expand="block">Open Sheet Modal</ion-button>

      <ion-modal
        trigger="open-modal"
        :is-open="false"
        :initial-breakpoint="1"
        :breakpoints="[0, 1]"
        :handle="false"
        :can-dismiss="false"
      >
        <div class="block">
          <div class="header">
            <span>Header</span>
            <span>Icon</span>
          </div>
          <CustomButton button-text="Click me" />
        </div>
      </ion-modal>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonButton,
  IonModal,
  IonItem,
  IonList,
  IonAvatar,
  IonImg,
  IonLabel,
  IonSearchbar,
} from "@ionic/vue";
import ExploreContainer from "@/components/ExploreContainer.vue";
import CustomButton from "@/components/CustomButton.vue";
</script>

<style>
.header {
  display: flex;
  justify-content: space-between;
  padding: 20px;
}
.block {
  width: 100%;
  height: 300px;

  background-color: orange;
}

ion-modal {
  --height: auto;
}
</style>
