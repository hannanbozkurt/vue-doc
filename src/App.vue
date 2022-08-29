<template>
  <div>
   <!-- v-model bir değişkeni template kısmındaki bir input' veya benzer öğeye 
   eşitlemek için kullannılan bir atrributedir -->
    <input v-model="dataa" />
    <!--String Interpolition vue js'te bir değişkenin değerini template içinde göstermek için bunu kullanırız -->
    {{ dataa }}
    <!--@click/v-on:click bir butona bir fonksiyon veya eylem tanımlanmak istendiği zaman bu şekilde kullanılır -->
    <button @click="nmbr++">
      {{ nmbr }}
    </button>
    {{ item }}
    <button @click="setNumber()">besle carp</button>
  </div>
</template>

<script>
//import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  //DATA: değişkenlerin tanımlandığı yer
  data() {
    return {
      dataa: null,
      nmbr: 1,
    };
  },
  //METHODS: Fonksiyon ve metodların tanımlandığı yer.
  methods: {
    setNumber() {
      console.log("bes ile carptım carpmaz olaydım");
      this.nmbr = this.nmbr * 3;
    },
  },
  //En sık kullanılan küçük matematik işlemlerinin saklandığı yer
  computed: {
    item() {
      return this.nmbr * 5;
    },
  },
  //Component MOUNTE edilirken çalışması istenen fonksiyonlar ve yapılması istenen işlemler burada tutulur.
  mounted() {
    for (let i = 0; i < 5; i++) {
      this.setNumber();
    }
    this.setNumber();
    console.log(this);
  },
  //İçine yazılan daha önce tanımlı değişkenin anlık eventinı takip ederek istediğin aksiyonu alır
  watch: {
    dataa() {
      console.log(this.dataa);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
