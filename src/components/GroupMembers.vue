<template>
    <v-responsive class="align-center fill-height mx-auto" max-width="900">
      <v-row justify="center">
        <v-col
          v-for="(member, index) in members"
          :key="index"
          cols="12"
          sm="6"
          md="4"
        >
          <v-card class="hoverable-card" outlined>
            <v-img :src="member.image" height="200px"></v-img>
            <v-card-title class="text-center">{{ member.name }}</v-card-title>
            <v-card-subtitle class="text-center mb-2">{{
              member.role
            }}</v-card-subtitle>
            <!-- <v-card-text class="text-center">{{
              member.description
            }}</v-card-text> -->
          </v-card>
        </v-col>
      </v-row>
    </v-responsive>
</template>

<script setup>
const members = [
  {
    name: "Dima Zaichenko",
    role: "Member",
    description: "Passionate about creating beautiful user interfaces.",
    image: "https://via.placeholder.com/200",
  },
  {
    name: "Charles Letellier",
    role: "Member",
    description: "Loves working on efficient backend systems.",
    image: "https://via.placeholder.com/200",
  },
  {
    name: "Joshua Yarussky",
    role: "Leader",
    description: "Focuses on creating seamless user experiences.",
    image: "https://via.placeholder.com/200",
  },
  {
    name: "Mohammed Sarhat",
    role: "Presenter",
    description: "Ensures timely and organized project deliveries.",
    image: "https://i.imgur.com/tz2lisu.jpeg",
  },
  {
    name: "Patrick Favret",
    role: "Member",
    description: "Enjoys working across the stack, from frontend to backend.",
    image: "https://via.placeholder.com/200",
  },
  {
    name: "Roman Rodchenkov",
    role: "Member",
    description: "Passionate about software quality and testing.",
    image: "https://via.placeholder.com/200",
  },
];
</script>

<style scoped>
.hoverable-card {
  transition: transform 0.3s ease-in-out;
  cursor: pointer;
}

.hoverable-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
</style>
