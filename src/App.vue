<template>
  <div class="background">
    <Card v-for="card in cards" :card="card" :key=card></Card>
  </div>
</template>

<script>
import Card from "./components/Card.vue";

export default {
  name: "App",
  data() {
    return {
      cards: [
        {
          title: "المادية والفردانية",
          presenter: "عمرو إبراهيم",
          location: "Location 1",
          time: "10/24 12:00ص",
          type: "محاضرة",
          gender: "الكل",
          image:"https://woz-u.com/wp-content/uploads/2021/04/woz-what-is-data-mining.jpg",
        },
        {
          title: "مقدمة إلى اللسان الياباني",
          presenter: "نبيل بن عبداللطيف الصياد",
          location: "Location 2",
          time: "10/20 09:00ص",
          type: "محاضرة",
          gender: "الكل",
          image: "https://m.media-amazon.com/images/I/313dtY-LOEL.jpg",
        },
        {
          title: "Power BI لذكاء البيانات",
          presenter: "سجى السعداوي",
          location: "Location 3",
          time: "10/24 10:00ص",
          type: "محاضرة",
          gender: "الكل",
          image: "https://cdn.shopify.com/s/files/1/0899/1470/files/banner-family-hub-peppa-pig_9eeeded8-532c-415d-b536-65277db33261.png",
        },
        {
          title: "تعريف بمزايا دسكورد",
          presenter: "نبيل بن عبداللطيف الصياد",
          location: "Location 3",
          time: "10/24 02:00م",
          type: "محاضرة",
          gender: "الكل",
          image: "https://cdn.shopify.com/s/files/1/0899/1470/files/banner-family-hub-peppa-pig_9eeeded8-532c-415d-b536-65277db33261.png",
        },
      ],
    };
  },
  components: {
    Card,
  },
};
</script>

<style scoped>
.background {
  width: 100%;
  display: grid;
  place-items: center;
  padding: 4%;
  
}
</style>