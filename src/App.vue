
<template>
  <form action="">
    <input type="text" placeholder="name" v-model="usName">
    <input type="password" placeholder="password" v-model="usPass">
    <input type="email" placeholder="email" v-model="usEmail">

    <button @click="sendData()" type="button">xddd</button>
  </form>



  <div v-if="us.length == 0">
    <p className="er">Никого нет</p>
    <p className="er">{{ er }}</p>
  </div>

  <div v-for="(u, index) in us" :key="index">
      <p>{{ u.name }} {{ u.pass }} {{ u.email }}</p>
  </div>
</template>

<script>


export default{
  data(){
    return{
        us: [],
        er:'',
        usName: '',
        usPass: '',
        usEmail:''
      }
  },
  methods: {
    sendData() {
      if(this.usName==""){
        this.er = "Опа нихера!"
        return;
      }
      if(this.usPass==""){
        this.er = "Пароль падла!"
        return;
      }
      if(this.usEmail==""){
        this.er = "Пиши почту паскуда!"
        return;
      }

      this.us.push({
        name: this.usName,
        pass: this.usPass,
        email: this.usEmail
      })
    }
  }
}
</script>


<style scoped>
h3{
  color: blue;
}
p{
  color: red;
}

.er{
  font-size: 20pt;
}
</style>
