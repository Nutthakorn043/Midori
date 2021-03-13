<template>
  <div class="login" >
    <div class="bg">
    <h1>Sign up</h1>
      <b-row class="text-center">
        <b-col></b-col>
        <b-col class="8">
          <b-card-text>
            <b-form @submit.stop.prevent>
              <label for="text-password"><p>Email</p></label>
              <b-input-group>
                <b-input-group-prepend is-text>
                  <b-icon icon="envelope"></b-icon>
                </b-input-group-prepend>
                <b-form-input
                  type="email"
                  id="text-email"
                  aria-describedby="password-help-block"
                ></b-form-input>
              </b-input-group>
            </b-form>
          </b-card-text>
        </b-col>
        <b-col></b-col>
      </b-row>
      <br />
      <b-row class="text-center">
        <b-col></b-col>
        <b-col class="8">
          <b-card-text>
            <b-form @submit.stop.prevent>
              <label for="text-password"><p>Password</p></label>
              <b-input-group>
                <b-input-group-prepend is-text>
                  <b-icon icon="lock"></b-icon>
                </b-input-group-prepend>
                <b-form-input
                  type="password"
                  id="text-password"
                  aria-describedby="password-help-block"
                ></b-form-input>
              </b-input-group>
            </b-form>
          </b-card-text>
        </b-col>
        <b-col></b-col>
      </b-row>
      <br />
      <b-button variant="danger" @click="login">Login by Google</b-button>&nbsp;
      <b-button variant="info">Login</b-button>&nbsp;
      <b-button href="/register" variant="primary">Sign in</b-button>
      </div>
    </div>
    
</template>

<script>
import firebase from "firebase/app";
export const auth = firebase.auth();
export default {
  methods: {
    login() {
      const provider = new firebase.auth.GoogleAuthProvider();
      auth
        .signInWithPopup(provider)
        .then((result) => {
          /** @type {firebase.auth.OAuthCredential} */
          const credential = result.credential;
          const token = credential.accessToken;
          console.log(token);
          const user = result.user;
          console.log("User = " + user);
          this.$router.replace("/product");
        })
        .catch((error) => {
          const errorCode = error.code;
          console.log(errorCode);
        });
    },
    logout() {
      firebase
        .auth()
        .signOut()
        .then(() => {
          console.log("Sign-out successful");
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style>
.login {
  margin-block-end: 5%;
  size: 100%;
  background-image: url();
}
.login h1{
margin-top: 5%;
color: rgb(255, 255, 255);
}
.login p {
  margin-top: 10px;
  font-size: 25px;
  color: rgb(255, 255, 255);
}
 body, html {
    height: 100%;
  }
  .bg {
    /* The image used */
    background-image: url("https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/da033e72-0c02-4f60-a051-5fbf5205e7e8/d2uolv5-34388794-cda3-4698-a432-327f020d3e49.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3sicGF0aCI6IlwvZlwvZGEwMzNlNzItMGMwMi00ZjYwLWEwNTEtNWZiZjUyMDVlN2U4XC9kMnVvbHY1LTM0Mzg4Nzk0LWNkYTMtNDY5OC1hNDMyLTMyN2YwMjBkM2U0OS5naWYifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6ZmlsZS5kb3dubG9hZCJdfQ.5d5FbSceDxrgosqRmKudh0UrqNnxfeayBEkYGh1LfQI");

    /* Full height */
    height: 100%;

    /* Center and scale the image nicely */
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
  .bg h1 {
    margin-top: 5%;
color: rgb(255, 255, 255);
  }
</style>
