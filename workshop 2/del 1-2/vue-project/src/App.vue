<template>
  <BaseLayout>
    
    <template v-slot:header>
      <header>
        <h1>Football Teams Allsvenskan</h1>
      </header>
    </template>

    <template v-slot:main>
      <main>
        <div class="theBody">
          <Card v-for="team in footballTeams" :key="team.name" :card-data="team" @button-clicked="handleButtonClick">
            See how many titles {{ team.name }} has
          </Card>
        </div>
      </main>
    </template>

    <template v-slot:footer>
      <footer>
        <p>Football Teams App</p>
      </footer>
    </template>
  </BaseLayout>
</template>

<script>
import BaseLayout from "./components/BaseLayout.vue";
import Card from "./components/Card.vue";

export default {
  components: {
    BaseLayout,
    Card,
  },
  data() {
    return {
      footballTeams: [
        {
          name: "Djurgården",
          titles: 17,
          city: "Stockholm",
        },
        {
          name: "Hammarby",
          titles: 2,
          city: "Stockholm",
        },
        {
          name: "IFK Norrköping",
          titles: 19,
          city: "Norrköping",
        },
        {
          name: "Malmö FF",
          titles: 38,
          city: "Malmö",
        },
      ],
    };
  },
  methods: {
    handleButtonClick(titles) {
      console.log('Button clicked for team. Titles:', titles); 
    },
  },
};
</script>

<style>
.theBody {
  display: flex;
  gap: 20px;
  justify-items: center;
  
}
</style>