<template>
  <b-container>
    <b-row>
      <b-col cols="6" offset="3">
        <b-form @submit="onSubmit" v-if="show">
          <b-form-group id="signInEmailLable"
                        label="Email"
                        label-for="signInEmail"
                        description="">
            <b-form-input id="signInEmail"
                          type="email"
                          v-model="form.email"
                          required
                          placeholder="example@gmail.com">
            </b-form-input>
          </b-form-group>
          <b-form-group id="signInPasswordLabel"
                        label="Password"
                        label-for="signInPassword">
            <b-form-input id="signInPassword"
                          type="password"
                          v-model="form.password"
                          required
                          placeholder="password">
            </b-form-input>
          </b-form-group>
          <b-button type="submit" variant="primary">Sign In</b-button>
        </b-form>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          email: '',
          password: ''
        },
        show: true
      }
    },
    methods: {
      onSubmit(evt) {
        evt.preventDefault();
        alert(JSON.stringify(this.form));
      },
      onReset(evt) {
        evt.preventDefault();
        /* Reset our form values */
        this.form.email = '';
        this.form.password = '';
        /* Trick to reset/clear native browser form validation state */
        this.show = false;
        this.$nextTick(() => {
          this.show = true
        });
      }
    }
  }
</script>
<style scoped></style>
