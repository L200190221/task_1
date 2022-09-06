<template>
  <div class="container">
    <div class="nav">
      <h1>Resume</h1>
    <h2>Muhammad Mubarok</h2>
    <p>Nama saya Muhammad Mubarok tempus, tellus eget condimentum rhoncus, sem quam semper libero, sit amet adipiscing
      sem neque sed ipsum. Nam quam nunc, blandit vel, luctus pulvinar, hendrerit id, lorem. Maecenas nec odio et ante
      tincidunt tempus. Donec vitae sapien ut libero venenatis faucibus. Nullam quis ante. Etiam sit amet orci eget eros
      faucibus tincidunt. Duis leo. Sed fringilla mauris sit amet nibh. Donec sodales sagittis magna. Sed consequat, leo
      eget bibendum sodales, augue velit cursus nunc,'
    </p>
    </div>
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
              {{ data.title }} - {{ data.name }} 
            <p class='show' v-if="data.showproject">
              {{data.date +" Project :" + data.project }}
            </p>
          </li>
        </ul>
      </div>
    </div>
    <div class="footer" >
      <h3>Contact Me</h3>
      <p>Name :</p>
      <input type="text" v-model="contact.name" placeholder="masukkan nama" required />
      <p>Email :</p>
      <input type="email" v-model="contact.email" placeholder="example@gmail.com" required />
      <p>Note :</p>
      <textarea cols="30" rows="10" v-model="contact.note" placeholder="input note" required/><br>
      <button @click="SubmitContact">Submit</button>
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
          title: 'Junior Front End',
          name: 'PT.Qatros',
          date: 'Agustus-Sekarang',
          project: 'abc',
          showproject: false,
        },
        {
          id: '3',
          title: 'Junior Front End',
          name: 'PT.Qatros',
          date: 'Agustus-Sekarang',
          project: 'abc',
          showproject: false,
        },
        
      ],
      skills: [
        {nama: "desain", prosentase: "100%", number: "5.0/5.0" },
        {nama: "css", prosentase: "80%", number: "3.0/5.0" },
        {nama: "html", prosentase: "50%", number: "5.0/5.0" },
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
      alert(
        "terimakasih sudah submit "
      );
    },
  },
}

</script>

<style>
*{
  margin: 0%;
  padding: 0%;
}
.nav,.sidebar,.maincontent,.footer{
  margin-top: 10px;
}
.container{
  line-height: 2;
  margin-left: 10px;
  margin-right: 10px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  border-style: groove;
  border-radius: 10px;
  align-content: center;
}
.nav {
  background: yellow;
}

.maincontent{
  justify-content: space-around;
  display: flex;
  width: 50%;
  min-height: 224px;
  background: blue;
  justify-content: top;
  align-items: top;
}
.sidebar{
  width: 50%;
  background: rgb(255, 0, 0);
  justify-content: left;
  align-items: left;
}
.skill{
  
}
.prosentase {
  background: violet;
}
.footer{
  justify-content: space-around;
  width: 100%;
  height: 100%;
  align-content: center;
  text-align: center;
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

