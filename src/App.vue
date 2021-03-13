<template>
  <div id="app">
    <div id="navbar">
  <a href="/" id="logo"><img src="https://drive.google.com/uc?id=1YomJCZwim6dMXB64QNxlWHHM_f2Q27TK" style="max-width: 10rem;" alt=""></a>
  <div id="navbar-right">
    <a href="/product">Shop all</a>
    <a href="#about">About</a>
    <a href="/register">Contact</a>
    <a href="/login"><b-icon icon="person-circle"></b-icon> Login</a>
    <a><router-link to="/about"><b-icon icon="cart3"></b-icon>Basket</router-link></a>
  </div>
</div>
    <router-view />
    <div class="footer">
  <p>Footer</p>
</div>
</div>
  
  
</template>

<style>
#navbar {
  overflow: hidden;
  background-color: #f1f1f1;
  padding: 90px 10px; /* Large padding which will shrink on scroll (using JS) */
  transition: 0.4s; /* Adds a transition effect when the padding is decreased */
  position: fixed; /* Sticky/fixed navbar */
  width: 100%;
  top: 0; /* At the top */
  z-index: 99;
  height: 1px;
}

/* Style the navbar links */
#navbar a {
  float: left;
  color: black;
  text-align: center;
  padding: 12px;
  text-decoration: none;
  font-size: 18px;
  line-height: 25px;
  border-radius: 4px;
}

/* Style the logo */
#navbar #logo {
  font-size: 35px;
  font-weight: bold;
  transition: 0.4s;
}

/* Links on mouse-over */
#navbar a:hover {
  background-color: #ddd;
  color: black;
}

/* Style the active/current link */
#navbar a.active {
  background-color: dodgerblue;
  color: white;
}

/* Display some links to the right */
#navbar-right {
  float: right;
}

/* Add responsiveness - on screens less than 580px wide, display the navbar vertically instead of horizontally */
@media screen and (max-width: 580px) {
  #navbar {
    padding: 20px 10px !important; /* Use !important to make sure that JavaScript doesn't override the padding on small screens */
  }
  #navbar a {
    float: none;
    display: block;
    text-align: left;
  }
  #navbar-right {
    float: none;
  }
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#left {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
}
#right {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: right;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}
#nav a {
  font-weight: bold;
  color: #ffffff;
}
#nav a.router-link-exact-active {
  color: #42b983;
}
.footer {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  background-color: rgb(34, 104, 77);
  color: white;
  text-align: center;
}
.hh1{
  font-variant: normal;
}
</style>

