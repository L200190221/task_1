<template>
  <div class="container">
    <div class="nav">
      <h1>RESUME</h1>
    </div>
    <h2>Muhammad Mubarok</h2>
      <p>Nama saya Muhammad Mubarok tempus, tellus eget condimentum rhoncus, sem quam semper libero, sit amet adipiscing
      sem neque sed ipsum. Nam quam nunc, blandit vel, luctus pulvinar, hendrerit id, lorem. Maecenas nec odio et ante
      tincidunt tempus. Donec vitae sapien ut libero venenatis faucibus. Nullam quis ante. Etiam sit amet orci eget eros
      faucibus tincidunt. Duis leo. Sed fringilla mauris sit amet nibh. Donec sodales sagittis magna. Sed consequat, leo
      eget bibendum sodales, augue velit cursus nunc,'
    </p>
    <div class="sidebar"  style="float:left;">
      <h4>Skills</h4>
      <div class="skill">
        <ul>
          <li v-for="Skill in skills" :key="Skill.nama">
            <p>{{ Skill.nama + " " + Skill.number }}</p>
            <div class="prosentase" :style="{width: Skill.prosentase}">&nbsp</div>
          </li>
        </ul>
      </div>
    </div>
    <div class="maincontent">
      <div class="pengalaman">
        <h4>Experience</h4>
        <ul>
          <li v-for="data in pengalaman" :key="data.id" @click="ShowProject(data)">
             {{ data.id }} {{ data.title }} - {{ data.name }}
            <p class='show' v-if="data.showproject">
              {{data.date +" Project :" + data.project }}
            </p>
          </li>
        </ul>
      </div>
    </div>
    <div class="footer" >
      <h3>Contact Me</h3>
      <form @submit="SubmitContact">
        <p>Name :</p>
        <input type="text" v-model="contact.name" placeholder="masukkan nama" required />
        <p>Email :</p>
        <input type="email" v-model="contact.email" placeholder="example@gmail.com" required />
        <p>Note :</p>
        <textarea cols="30" rows="10" v-model="contact.note" placeholder="input note" required/><br>
        <button>Submit</button>
      </form>
    </div>
  </div>
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
          date: 'Agustus-Sekarang',
          project: 'abc',
          showproject: false,
        },
        {
          id: '2',
          title: 'Desainer',
          name: 'Santri Letter',
          date: 'november-februari',
          project: 'desain kalender,desain pamflet, dll',
          showproject: false,
        },
      ],
      skills: [
        {nama: "desain", prosentase: "90%", number: "4.5/5.0" },
        {nama: "css", prosentase: "70%", number: "3.5/5.0" },
        {nama: "html", prosentase: "80%", number: "4.0/5.0" },
        {nama: "vue", prosentase: "50%", number: "2.5/5.0" },
      ],
      contact: {
        name: "",
        email: "",
        note: "",
      },
    };
  },
  methods: {
    ShowProject(data) {
      data.showproject = !data.showproject;
    },
    SubmitContact(){
      if (this.SubmitContact=="") {
        alert ("tidak boleh kosong");
      }else {
        alert ("trima kasih")
      }
    },
  },
}

</script>

<style>
*{
  margin: 0%;
  padding: 0%;
  align-content: center;
}
h1 {
  font-size: 50px;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  font-weight: bold;
}
.nav,.sidebar,.maincontent,.footer{
  margin-top: 10px;
}
p {
  text-align: center;
}
.container{
  text-indent: 2em;
  margin-left: 100px;
  color: rgb(0, 0, 0);
  background-color: rgb(131, 131, 240);
  align-items: center;
  text-align: center;
  width: 600px;
  line-height: 2;
  margin-left: 10px;
  margin-right: 10px;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  border-style: groove;
  border-radius: 10px;
  align-content: center;
}
.nav {
  
}
.maincontent{
  justify-content: space-around;
  display: flex;
  min-height: 224px;
  justify-content: top;
  align-items: top;
}
.sidebar{
  width: 50%;
  min-height: 224px;
  justify-content: left;
  align-items: left;
}
li {
  list-style-type:none ;
}
.skill
h1,h2,h3,h4{
  border: black 2px solid;
  min-width: 300px;
  background-color: rgb(45, 45, 163);
  color: black;
}
.skill{
  
}
.prosentase {
  border-radius: 8px;
  height: 15px;
  background-color: rgb(196, 196, 255);
  border: 1px black solid;
}
.footer p {
  text-align: center;
}
.footer{
  justify-content: space-around;
  width: 100%;
  height: 100%;
  align-content: center;
  text-align: center;
}
input, textarea {
  width: 300px;
  border-radius: 5px;
  background-color: rgb(196, 196, 255);
}
input {
    height: 30px;
}
button{
  font-size: 20px;
  padding: 10px ;
  border-radius: 10px;
  background-color: rgb(196, 196, 255);
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

