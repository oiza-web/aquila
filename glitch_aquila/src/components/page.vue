<template>
  <main id="wrapper">
    <div>
      <h1 class="header">{{aquila.name }}</h1>
    </div>
    <div class="imgBx">
      <img src="../assets/aquila2.jpg">
        </div>

  <section  class="container">
    <div id=left class="col-1  ">
        
    </div>
    
    <div id="right" class="col-1">
      <div class=" social"> 
        <ul class="icons">
    
        <li><a href=""><v-icon color="#fff">mdi-twitter </v-icon></a></li>    
        <li><a href=""><v-icon color="#fff">mdi-twitter </v-icon></a></li>    
        <li><a href=""><v-icon color="#fff">mdi-snapchat </v-icon></a></li>
        <li><a href=""><v-icon color="#fff">mdi-email</v-icon></a></li>    
        </ul>
      </div>
    </div>
  </section>
  <div class="bottom">
    <ul class="nav">
    <li><h1>HOME</h1></li>
    <li><h1>ABOUT</h1></li>
    <li><img class="bottom-image" src="../assets/aquilq.jpeg" alt=""></li>
    <li><h1>GALLERY</h1></li>
    <li><h1>CONTACT</h1></li>
  </ul>

  </div>
  
  
</main>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
    aquila : ''
    }
  },
  mounted () {
    axios
      .get('https://hirng-x2021.glitch.me/api')
      .then(response =>this.aquila = response.data);

    console.log("got here",this.aquila.name)
      
  }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

* {
  box-sizing: border-box;
}

body {
  font-size: 100%;
  font-family: "Open-Sans", sans-serif;
  line-height: 100%;
}

main {
  width: 100%;
  height: 100%;
}


.wrapper,
.container,
.col-1
{
  display: flex;
  flex: 1 100%;
}

.container {
  flex-flow: column nowrap;
  min-height: 90vh;
  width:100%;
}


.col-1{
  justify-content: center;
}

.imgBx{
    grid-gap: 15px;
    position: fixed; 
    top: 20%;
    left: 35%;
    
    background:#cb2964;
    border-radius: 4px;
    box-shadow:0 2px 10px rgba(0,0,0,.2);
  }

  img{
    width: 60%;
    height: 70%;
    position: unset;
  }
.header{
  position: fixed; 
  top: 3%;
  left: 32%;
  color: #fff;
  letter-spacing: 0.3em;
}

li{
  list-style-type: none;
  padding: 20px;
  right: 50%;
}


a{
  text-decoration: none;
  
}


@media (min-width: 61.25em) {
  .container {
    flex-flow: row nowrap;
 }
  .col-2 {
    padding: 11% 9%;
  }
}

/* Styling the rest of the items  */


#left{
  background: #bd0f4e;
  color:white;
   height: 700px;
}

 #right{
  background: #cb2964;
  color: white;
} 


.social {
  padding-top:30%;
  padding-left: 60%;
}
  
.nav {
 
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  color: #fff;
  letter-spacing: 0.5em;
}

.nav li {
  float: left;
  padding-left: 50px;
  font-weight: 100;
  font-size: .5em;
}

.bottom{
  position: fixed;
  bottom: 2%;
  margin-left: 250px;

}


.bottom-image {
  width: 80px;
  height: 80px;
  border-radius: 100%;
}


</style>
