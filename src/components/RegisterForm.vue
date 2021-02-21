<template>
  <form v-on:submit="handleFormSubmit">
    <Steps class="steps__desktop" :classNames="{ _is_transparent: true }" />

    <div class="form__entry">Please enter your details below</div>

    <div class="d-flex justify-content-center align-items-center">
      <div class="form__radioWrapper">
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            name="genderMale"
            id="genderMale"
            value="genderMale"
            v-model="selectedGender"
          />

          <label class="form-check-label" for="genderMale">
            De heer
          </label>
        </div>
      </div>

      <div class="form__radioWrapper">
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            name="genderFemale"
            id="genderFemale"
            value="genderFemale"
            v-model="selectedGender"
          />

          <label class="form-check-label" for="genderFemale">
            Mevrouv
          </label>
        </div>
      </div>
    </div>

    <div class="input-group mt-3 mb-3">
      <input type="text" class="form-control form__input" v-model="firstName" placeholder="First name" />

      <input type="text" class="form-control form__input" v-model="lastName" placeholder="Last name" />
    </div>

    <div class="input-group mt-2 mb-3">
      <input type="text" class="form-control form__input" v-model="email" placeholder="Email" />
    </div>

    <div class="input-group mt-2 mb-3">
      <label class="form-label d-flex align-items-center" for="dateOfBirth">
        <img class="form__date__icon" src="../assets/icons/calendar.svg" />
        <b>Date of birth:</b>
      </label>

      <date-dropdown min="1960" max="2017" v-model="selectedDate" class="form__date" />
    </div>

    <div class="input-group mt-2 mb-3 _is_hidden_desktop">
      <input type="text" class="form-control form__input" v-model="address" placeholder="Address" />
    </div>

    <div class="input-group mt-2 mb-3 _is_hidden_desktop">
      <input type="text" class="form-control form__input" v-model="phonenumber" placeholder="Phone No." />
    </div>

    <button type="submit" class="btn btn-primary mt-3 form__button">
      Accept T&C's and enter now
    </button>

    <div class="form__privacyImage" />
  </form>
</template>

<script>
import DateDropdown from 'vue-date-dropdown';
import Steps from './Steps';

export default {
  name: 'RegisteForm',

  components: {
    DateDropdown,
    Steps,
  },

  data() {
    return {
      selectedDate: '',
      selectedGender: '',
      firstName: '',
      lastName: '',
      email: '',
      address: '',
      phonenumber: '',
    }
  },

  methods: {
    handleFormSubmit(event) {
      event.preventDefault();

      this.$emit('FORM_SUBMITTED', { ...this.data });
    }
  }
};
</script>

<style scoped>

.form__entry {
  margin-bottom: 8px;
  font-size: 18px;
  font-weight: bold;
}

.form__input {
  margin-right: 16px;
  padding-left: 0;
  background-color: transparent;
  border: none;
  border-bottom: 1px solid #fff;
  color: #fff;
  font-size: 18px;
  border-radius: 0;
}

.form__date__icon {
  margin: 0 8px 4px 0;
}

.form__radioWrapper {
  background: rgba(255, 255 , 255, .1);
  border-radius: 4px;
  padding: 14px;
}

.form__radioWrapper:first-child {
  margin-right: 16px;
}

.form__button {
  font-size: 15px;
  font-weight: bold;
  padding: 16px 24px;
  text-transform: uppercase;
  border-radius: 40px;
  background-color: #0046A7;
}

.form__privacyImage {
  height: 22px;
  width: 210px;
  background: url('../assets/privacyStatement.svg');
  margin: 24px auto;
}

.form__input::placeholder {
  color: #fff;
}

.input-group > .form__input:last-child {
  margin: 0;
}

input:focus {
  outline: none !important;
}

.form__date {
  display: flex;
  justify-content: space-between;
  width: 100%;
}

.form-check-label {
  font-size: 16px;
}

@media only screen and (min-width: 768px) {
  ._is_hidden_desktop {
    display: none;
  }
}

</style>
