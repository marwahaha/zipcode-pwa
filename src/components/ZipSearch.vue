<template>
   <ion-grid>
      <form @submit.prevent="onSubmit()">
         <ion-col>
            <ion-item>
               <ion-label>Zipcode: </ion-label>
               <ion-input :value="zip" @input="zip = $event.target.value" placeholder="Enter country Zipcode" name="zip"></ion-input>
            </ion-item>
         </ion-col>
         <ion-col>
            <ion-button type="submit" color="primary" expand="block">Find</ion-button>
         </ion-col>
      </form>
   </ion-grid>
</template>

<script>
export default {
   name: "ZipSearch",
   data() {
      return {
         zip: ""
      };
   },
   methods: {
      onSubmit() {
         console.log(this.zip);
         // Zip Regex, this will be true or false
         const isValidZip = /(^\d{5}$)|(^\d{5}-\d{4}$)/.test(this.zip);
         if (!isValidZip) {
            this.showAlert();
         } else {
         }
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

