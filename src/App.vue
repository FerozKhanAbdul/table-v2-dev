<template>
  <!-- <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
    <router-link to="/table"></router-link>
  </nav> -->
  <router-view/>
</template>

<style lang="scss">
@font-face {
  font-family: OpenSans;
  src: url("~@/assets/OpenSans.ttf") format("opentype");
}
// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   // text-align: center;
//   // color: #2c3e50;
// }
// table,th,td {
//   border: 1px solid #d8d8d8;
//   border-collapse: collapse;
//   color: #191A15;
// }
th,td{
  padding:10px;
  border:1px solid #d8d8d8
}
// table{
//   border-radius: 8px;
// }
// thead{
  // background: #54bd95;
// }
// nav {
//   padding: 30px;

//   a {
//     font-weight: bold;
//     color: #2c3e50;

//     &.router-link-exact-active {
//       color: #42b983;
//     }
//   }
// }
</style>
