<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar slot="bottom">
        <ion-tab-button
          tab="tab1"
          href="/tabs/tab1"
          :class="{ selected: selectedTab === 'tab1' }"
        >
          <ion-icon aria-hidden="true" :icon="triangle" />
        </ion-tab-button>

        <ion-tab-button
          tab="tab2"
          href="/tabs/tab2"
          :class="{ selected: selectedTab === 'tab2' }"
        >
          <ion-icon aria-hidden="true" :icon="ellipse" />
        </ion-tab-button>

        <ion-tab-button
          tab="tab3"
          href="/tabs/tab3"
          :class="{ selected: selectedTab === 'tab3' }"
        >
          <ion-icon aria-hidden="true" :icon="square" />
        </ion-tab-button>

        <ion-tab-button
          tab="tab4"
          href="/tabs/tab2"
          :class="{ selected: selectedTab === 'tab4' }"
        >
          <ion-icon aria-hidden="true" :icon="square" />
        </ion-tab-button>

        <ion-tab-button
          tab="tab5"
          href="/tabs/tab2"
          :class="{ selected: selectedTab === 'tab5' }"
        >
          <ion-icon aria-hidden="true" :icon="square" />
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script setup lang="ts">
import {
  IonTabBar,
  IonTabButton,
  IonTabs,
  IonLabel,
  IonIcon,
  IonPage,
  IonRouterOutlet,
} from "@ionic/vue";
import { ellipse, square, triangle } from "ionicons/icons";
import { ref, onMounted } from "vue";
import { useRoute, useRouter } from "vue-router";

const selectedTab = ref("tab1");
const router = useRouter();

onMounted(() => {
  const currentRoute = useRoute();
  selectedTab.value = currentRoute.path.split("/").pop() || "tab1";
});

router.afterEach((to, from) => {
  selectedTab.value = to.path.split("/").pop() || "tab1";
});
</script>

<style>
ion-tab-button {
  transition: all 0.3s ease-in-out;
}

.selected {
  background-color: var(--ion-color-step-950);
  color: var(--background);
  border-radius: 100px;
  box-shadow: 0px 3px 6px 0px rgba(0, 0, 0, 0.1), 0px 1px 3px 0px rgba(0, 0, 0, 0.05),
    0px 0px 0px 1px rgba(100, 149, 237, 0.4);
}

ion-icon {
  font-size: 16px;
}

ion-tab-bar {
  --border: none;
  --background: var(--ion-color-step-150);
  margin: 16px 20px;
  padding: 7.5px 10px;
  border-radius: 50px;
}
</style>
