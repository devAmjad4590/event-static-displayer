<template>
  <div class="background">
    <Card v-for="card in cards" :card="card" :key="card"></Card>
  </div>
</template>

<script>
import Card from "./components/Card.vue";

export default {
  name: "App",
  async created() {
    await this.sortCards();
  },
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
          image:
            "https://woz-u.com/wp-content/uploads/2021/04/woz-what-is-data-mining.jpg",
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
          image:
            "https://cdn.shopify.com/s/files/1/0899/1470/files/banner-family-hub-peppa-pig_9eeeded8-532c-415d-b536-65277db33261.png",
        },
        {
          title: "تعريف بمزايا دسكورد",
          presenter: "نبيل بن عبداللطيف الصياد",
          location: "Location 3",
          time: "10/24 02:00م",
          type: "محاضرة",
          gender: "الكل",
          image:
            "https://cdn.shopify.com/s/files/1/0899/1470/files/banner-family-hub-peppa-pig_9eeeded8-532c-415d-b536-65277db33261.png",
        },
      ],
    };
  },
  methods: {
    // sorting cards based on the the time
    sortCards() {
      this.cards.sort((a, b) => {
        const parseTime = (timeString) => {
          let time = timeString.replace("ص", "AM").replace("م", "PM"); // replacing Arabic letters with English
          let [datePart, timePart] = time.split(" "); // splitting the date and time e.g. "10/24" = datePart and "12:00AM" = timePart

          let [month, day] = datePart.split("/").map(Number); // "splitting the month and day from datePart "10/24" = "10" and "24" and converting them to numbers

          let [hourMinute, period] = timePart.split(/(AM|PM)/); // Split by AM/PM from the timePart "12:00AM" = "12:00" and "AM"
          let [hour, minute] = hourMinute.split(":").map(Number); // Splitting the hour and minute from hourMinute "12:00" = "12" and "00" and converting them to numbers

          if (period === "PM" && hour < 12) hour += 12; // Convert PM to 24-hour format (12 PM = 12, 1 PM = 13, ..., 11 PM = 23)
          if (period === "AM" && hour === 12) hour = 0; // Convert midnight (12 AM) to 0 hour
          // to make the comparison easy

          // creating the date object following the format new Date(year, monthIndex, day, hours, minutes)
          return new Date(2024, month - 1, day, hour, minute); // monthIndex is zero-based
        };

        return parseTime(a.time) - parseTime(b.time);
      });
    },
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