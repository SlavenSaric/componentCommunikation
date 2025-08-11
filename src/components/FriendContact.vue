<template>
  <li>
    <h2>{{ name }}  {{ friendIsFavorite === '1' ? '(Favorite)' : '' }}</h2>
    <button @click="toggleDetails">
        {{ detailsAreVisible ? "Hide" : "Show" }} Details
    </button>
    <button @click="toggleFavorite">Toggle Favorite</button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone:</strong> {{ phoneNumber }}</li>
      <li><strong>Email:</strong> {{ email }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  props: ["name", "phoneNumber", "email", 'isFavorite'],
  data() {
    return {
      detailsAreVisible: false,
      friend: {
        id: "manuel",
        name: "Manuel Lorenz",
        phone: "432 34643 646",
        email: "manuel@local.com",
      },
      friendIsFavorite: this.isFavorite
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite(){
        if(this.friendIsFavorite === '1'){
            this.friendIsFavorite = '0' 
        }else{
            this.friendIsFavorite = '1'
        
    }
  },
}
}

</script>
