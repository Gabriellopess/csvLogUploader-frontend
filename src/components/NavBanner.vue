<template>
<section id="homepage">
  <section id="nav">
    <vs-navbar v-model="activeItem" class="nabarx">
      <div slot="title">
        <vs-navbar-title>
          Log Uploader
        </vs-navbar-title>
      </div>
      <vs-navbar-item index="0">
        <a href="#">Uploader</a>
      </vs-navbar-item>
      <vs-navbar-item index="2">
        <a href="#">Logs</a>
      </vs-navbar-item>
    </vs-navbar>
  </section>

  <section id="banner">
    <div id="img"></div>
    <div id="title"> RoboCIn csv log uploader</div>
  </section>  
</section>

  
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data:()=>({
    activeItem: 0
  })
}
</script>

<style scoped>
#homepage{
  font-family: 'Dongle', sans-serif;
}
#nav {
  background-color: rgb(163, 255, 176);
  /* border-radius: 0px 0px 30px 30px; */
}
.vs-navbar{
  height: 4em;
  -webkit-box-shadow: 0 4px 20px 0 rgb(0 0 0 / 30%);
  box-shadow: 0 4px 20px 0 rgb(0 0 0 / 50%);
}
.vs-navbar--title{
  font-size: 1.6rem;
  font-weight: 700;
}
.vs-navbar--item a{
  font-weight: 400;
  font-size: 1.5rem;
  margin-right: 20px;
}

#banner{
  padding: 1rem 1rem;
  margin: 0;
  width: 100%;
  background-image: url('../assets/headerbg3.jpg');
  background-repeat:no-repeat;
  background-attachment:scroll;
  background-position:center center;
  background-size:cover;
  height: 60vh;
  text-align: -webkit-center;

}

#img {
  width: 11em;
  height: 11em;
  margin-top: 55px;
  
  border-radius: 10%;
  background-color: white;
  background-image: url('../assets/rclogo.png');
  background-size: cover;
  background-repeat: no-repeat;
}

#title {
  margin: 30px;
  font-weight: 700;
  font-size:3rem;
  line-height:30px;
}
</style>
