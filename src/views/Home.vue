<template>
  <div class="home">
    <p>...</p>
    <p>二维码测试</p>
    <div>
      text:<input type="text" v-model="text">
      logo:<input type="text" v-model="logo">
      size:<input type="number" v-model="size">
      <br/>
      bgclor:<input type="color" v-model="bgColor">
      color: <input type="color" v-model="color">
      <br/>
      <button @click="getData">确定</button>
      <img :src ="datas"/>
      <p>{{datas}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'home',
  data(){
    return{
      text: 'hello,world!',
      logo: 'https://api.imjad.cn/qrcode/logo.png',
      size: 200,
      level: 'Q',
      bgColor: '#ffffff',
      color: '#000000',
      datas: ''
    }
  },
  methods: {
    getData(){
      this.datas = 'https://api.imjad.cn/qrcode?text='+this.text+
              '&logo='+this.logo+'&size='+this.size
              +'&level=H&bgcolor='+('%23'+this.bgColor.substring(1))+'&fgcolor='+('%23'+this.color.substring(1))
    }
  }
}
</script>
