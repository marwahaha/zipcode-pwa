<template>
   <div class="ion-page">
      <ion-header>
         <ion-toolbar>
            <ion-title>ZipApp</ion-title>
         </ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
         <ZipSearch v-on:get-zip="getZipInfo" />
      </ion-content>
   </div>
</template>

<script>
import ZipSearch from "../components/ZipSearch";
export default {
   name: "home",
   components: { ZipSearch },
   methods: {
      async getZipInfo(zip) {
         const res = await fetch(`https://api.zippopotam.us/us/${zip}`);
         if (res.status == 404) {
            this.showAlert();
         }
         const info = await res.json();
         console.log(info);
      },
      showAlert() {
         return this.$ionic.alertController
            .create({
               header: "Enter Zipcode",
               message: "Please enter a valid zipcode",
               buttons: ["OK"]
            })
            .then(a => a.present());
      }
   }
};
</script>
