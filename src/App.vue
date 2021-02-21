<template>
  <div id="app">
    <EditorialPage v-if="!registered" v-on:FORM_SUBMITTED="onFormSubmitted"/>

    <FinishPage v-if="registered" />

    <LoadingOverlay v-if="isLoading" />
  </div>
</template>

<script>
import EditorialPage from './pages/EditorialPage.vue';
import FinishPage from './pages/FinishPage.vue';
import LoadingOverlay from './components/LoadingOverlay.vue';


export default {
  name: 'App',

  components: {
    EditorialPage,
    FinishPage,
    LoadingOverlay,
  },

  data() {
    return {
      isLoading: false,
      registered: false,
    }
  },

  methods: {
    onFormSubmitted() {
      this.isLoading = true;

      setTimeout(() => { // fake an api call with the setTimeout function
        this.isLoading = false;
        this.registered = true;
      }, 2500)
    }
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
  font-weight: 500;
}

#app {
  font-family: Poppins, Avenir, Helvetica, Arial, sans-serif !important;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  max-width: 100vw;
  min-height: 100vh;
}

/** 3rd party libraries styles */
.date-dropdown-select {
  background-color: transparent !important;
  border: none !important;
  border-bottom: 1px solid #fff !important;
  color: #fff !important;
  border-radius: 0 !important;
}

.date-dropdown-select:focus {
  outline: none;
}

.form-check-inline {
  margin-right: 0;
}

/** Desktop styles */
@media only screen and (min-width: 768px) {
  .date-dropdown-select-wrapper {
    flex: 1;
    margin-right: 8px;
  }

  .date-dropdown-select-wrapper:last-child {
    margin-right: 0;
  }

  .date-dropdown-select {
    width: 100%;
  }
}

</style>
