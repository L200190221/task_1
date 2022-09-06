<template>
  <h1>Resume</h1>
  <h2>Muhammad Mubarok</h2>
  <p>Nama saya Muhammad Mubarok</p>
  <h4>Experience</h4>
  <ul>
    <li v-for="data in pengalaman" :key="data.id">
      {{ data.title }} - {{ data.name }} - {{ data.date }}
    </li>
  </ul>
  <h4>Skill</h4>
  <div class="skill">Desain</div>
  <div class="presentase" :style="{'width': presentase + '%'}"></div>


</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      pengalaman: [
        {
          id: '1',
          title: 'Junior Front End',
          name: 'PT.Qatros',
          date: 'Agustus-Sekarang'},
        {
          id: '2',
          title: 'Junior Front End',
          name: 'PT.Qatros',
          date: 'Agustus-Sekarang'
        }, 
        {
          id: '3',
          title: 'Junior Front End',
          name: 'PT.Qatros',
          date: 'Agustus-Sekarang'
        },
      ],
    }
  },
}
</script>

<style>
.container {
  font-family: sans-serif;
  text-align: left;
  color: #000000;
  margin-top: 60px;
  margin-left: 80px;

}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
