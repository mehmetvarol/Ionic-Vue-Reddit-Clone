<template>
  <ion-card>
    <ion-card-header>
      <ion-label style="color:white;"> {{post.title}} </ion-label>
    </ion-card-header>
    <ion-card-content>
      <ion-img :src="image"></ion-img>
      <ion-button color="tertiary" expand="full" @click="$router.go(-1)">
        Go Back
      </ion-button>
    </ion-card-content>
  </ion-card>
</template>

<script>
export default {
  props:['post'],
  data() {
    return {
      image:'',
    }
  },
  mounted() {
    this.image =this.post.preview.images[0].source.url.replace('&amp;','&'); //amp yerine & kullanmamız gerekiyor image gelmesi için
  },
}
</script>

<style>

</style>
