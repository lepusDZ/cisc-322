<template>
  <v-responsive class="align-center fill-height mx-auto" max-width="900">
    <div class="text-center">
      <h1 class="text-h2 font-weight-bold">Lorem Ipsum</h1>
    </div>

    <div class="py-4" />

    <v-row>
      <!-- Group Members Card -->
      <v-col cols="12">
        <v-card
          class="py-4 hoverable-card"
          color="surface-variant"
          prepend-icon="mdi-rocket-launch-outline"
          rounded="lg"
          variant="outlined"
          @click="$emit('scroll-to-section', 'group-members')"
        >
          <template #title>
            <h2 class="text-h5 font-weight-bold">Group Members</h2>
          </template>

          <v-overlay
            opacity=".06"
            scrim="primary"
            contained
            model-value
            persistent
          />
        </v-card>
      </v-col>

      <!-- Other cards -->
      <v-col cols="4">
        <v-card
          class="py-4 hoverable-card"
          color="surface-variant"
          prepend-icon="mdi-text-box-outline"
          rel="noopener noreferrer"
          rounded="lg"
          target="_blank"
          title="Assignment 1"
          variant="text"
          @click="$emit('scroll-to-section', 'assignment-1')"
        >
          <v-overlay
            opacity=".06"
            scrim="primary"
            contained
            model-value
            persistent
          />
        </v-card>
      </v-col>

      <v-col cols="4">
        <v-card
          class="py-4"
          color="surface-variant"
          prepend-icon="mdi-star-circle-outline"
          rel="noopener noreferrer"
          rounded="lg"
          target="_blank"
          title="Assignment 2"
          variant="text"
          @click="$emit('scroll-to-section', 'assignment-2')"
        >
          <v-overlay
            opacity=".06"
            scrim="primary"
            contained
            model-value
            persistent
          />
        </v-card>
      </v-col>

      <v-col cols="4">
        <v-card
          class="py-4"
          color="surface-variant"
          prepend-icon="mdi-widgets-outline"
          rel="noopener noreferrer"
          rounded="lg"
          target="_blank"
          title="Assignment 3"
          disabled
          variant="text"
        >
          <v-overlay
            opacity=".06"
            scrim="primary"
            contained
            model-value
            persistent
          />
        </v-card>
      </v-col>
    </v-row>
  </v-responsive>
</template>

<script setup></script>

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
