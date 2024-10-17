<template>
  <v-responsive class="align-center fill-height mx-auto" max-width="900">
    <v-row justify="center">
      <!-- PDF Card -->
      <v-col cols="12" sm="4">
        <v-card
          class="hoverable-card text-center"
          outlined
          @click="openLink(pdfLink)"
        >
        <v-icon class="mr-2" size="200">mdi-file-pdf-box</v-icon>
          <v-card-title class="text-center">
            Assignment {{ assignmentNumber }} PDF
          </v-card-title>
          <v-card-subtitle class="text-center mb-2">
            Click to view the PDF
          </v-card-subtitle>
        </v-card>
      </v-col>
      <!-- Presentation Card -->
      <v-col cols="12" sm="4">
        <v-card
          class="hoverable-card text-center"
          outlined
          @click="openLink(presentationLink)"
        >
        <v-icon class="mr-2" size="200">mdi-presentation-play</v-icon>
          <v-card-title class="text-center">
            Assignment {{ assignmentNumber }} Presentation
          </v-card-title>
          <v-card-subtitle class="text-center mb-2">
            Click to view the presentation
          </v-card-subtitle>
        </v-card>
      </v-col>
    </v-row>
  </v-responsive>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  assignmentNumber: {
    type: Number,
    required: true,
  },
  pdfLink: {
    type: String,
    required: true,
  },
  presentationLink: {
    type: String,
    required: true,
  },
});

const openLink = (url) => {
  window.open(url, '_blank');
};
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
