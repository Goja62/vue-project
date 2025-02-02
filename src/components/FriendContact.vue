<template>
  <li>
    <h2>{{ name }} {{ isFavorite ? '(Favorite)' : '' }}</h2>
    <button @click="toggleFavorite">Toggle Favorites</button>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? 'Hide' : 'Show' }} Details
    </button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone: </strong>{{ phoneNumber }}</li>
      <li><strong>Email: </strong>{{ emailAddress }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  // props: ['name', 'phoneNumber', 'emailAddress', 'isFavorite'],
  props: {
    id: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    phoneNumber: {
      type: String,
      required: true,
    },
    emailAddress: {
      type: String,
      required: true,
    },
    isFavorite: {
      type: Boolean,
      required: false,
      default: false,
      // validtor: (value) => {
      //   return value === '1' || value === '0';
      // },
    },
  },
  emits: ['toggle-favorite'],
  // emits: {
  //   'toggle-favorite': (id) => {
  //     if (id) {
  //       return true;
  //     } else {
  //       console.log('ID is mising...');
  //       return false;
  //     }
  // },
  // },
  data() {
    return {
      detailsAreVisible: false,
      // friend: {
      //   id: 'goja',
      //   name: 'Zoran Gortnar',
      //   phone: '2101914',
      //   email: 'gortnar@beograd.com',
      // },
      // friendIsFavorite: this.isFavorite,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      // if (this.friendIsFavorite === '1') {
      //   this.friendIsFavorite = '0';
      // } else {
      //   this.friendIsFavorite = '1';
      // }

      // this.friendIsFavorite = !this.friendIsFavorite;

      this.$emit('toggle-favorite', this.id);
    },
  },
};
</script>
