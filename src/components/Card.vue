<template>
  <v-card
    image="https://images.pexels.com/photos/1509534/pexels-photo-1509534.jpeg?auto=compress&cs=tinysrgb&w=600"
    class="card mb-9"
    rounded="lg"
  >
    <div class="card-content">
      <div>
        <v-img
          class="image-content"
          :src="card.image"
          alt="Card Image"
          cover
        ></v-img>
      </div>
      <div class="text-content">
        <h1 class="title">{{ card.title }}</h1>
        <p class="presenter">
          <strong>{{ card.presenter }}</strong>
        </p>
        <p class="left-text">{{ card.type }}</p>
        <p class="left-text">{{ card.location }}</p>
        <p class="left-text">{{ card.time }}</p>
      </div>
    </div>
  </v-card>
</template>

<script>
export default {
  name: "Card",
  props: {
    card: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=El+Messiri:wght@400..700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=El+Messiri&display=swap');

.card {
  width: 100%;
  max-width: 450px;
  height: auto;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  box-sizing: border-box;
  border: 4px solid black; /* Increase border width */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.8); /* Add shadow */
}

.card-content {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 100%;
}

.image-content {
  width: 100%;
  height: 100%;
  aspect-ratio: 16 / 9; /* Maintain a 16:9 aspect ratio */
}

.text-content {
  height: 100%;
  padding: 10px;
  text-align: right;
  background-color: rgba(
    248,
    248,
    249,
    0.9
  ); /* Add a semi-transparent background to make text readable */
}

.image-container {
  width: 100%;
  height: 100%;
  background: linear-gradient(to right, #F60862, #F93881); /* Add gradient from white to black */
}

.title {
  font-family: "El Messiri", sans-serif;
  font-optical-sizing: auto;
  font-size: 2.275em;
  font-weight: 700;
  margin-bottom: 0ch;
  font-style: normal;
  height: auto
}

.presenter {
  font-size: 1.4em;
  margin-top: 0%;
  margin-bottom: 2%;
  font-family: "El Messiri", sans-serif;
  font-optical-sizing: auto;
  font-weight: 600;
  font-style: normal;
  text-align: right;

}

p {
  font-family: "El Messiri", sans-serif;
  font-optical-sizing: auto;
  font-weight: 600;
  font-style: normal;
  line-height: 1.875;
  font-size: 1.175em;
  margin: 0; /* Remove default margin */
  text-align: right;
}

</style>