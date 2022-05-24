<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 3</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 3</ion-title>
            </ion-toolbar>
      </ion-header>

      <div id="cameraPreview" class="cameraPreview" style="text-align: center;">
        <ion-button @click="openCamera()" shape="round" id="openCam">Ouvrir la caméra</ion-button>
      </div>

      <div style="text-align: center;">
        <ion-button shape="round" id="takePhoto">Prendre la photo</ion-button>
        <ion-button @click="closeCamera()" shape="round">Fermer la caméra</ion-button>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton } from '@ionic/vue';
import { CameraPreview, CameraPreviewOptions } from '@capacitor-community/camera-preview';

export default defineComponent({
  name: 'Tab3Page',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonButton },
  methods: {
    openCamera() {
        const cameraPreviewOptions: CameraPreviewOptions = {
          position: 'front',
          parent: 'cameraPreview',
          className: 'cameraPreview'
        };
      CameraPreview.start(cameraPreviewOptions);
      console.log('feur');
  },
    closeCamera() {
        CameraPreview.stop();
  }
  }
});
</script>

