<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>

      <title>
        みんなの聞いてる音楽
      </title>

      <!-- 箱 -->
      <input v-model="newMusic" placeholder="好きな曲を入力してください"> 

      <!-- 追加ボタン -->
      <button v-on:click="addMusic()">追加</button>

      <h5>list</h5>

      <!-- newmusicという配列をループで表示 -->
      <ul>
        <li v-for="(music, i) in musics" v-bind:key="i">
          {{ music }}
        </li>
      </ul>
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>

<script>
export default {
  data(){
    return {
      // 配列
      musics: [],
      
      // 文字列
      newMusic: ""
    }
  },

  // メソッド、機能が買いてある
  // ここにランキング機能とか足してく（if文）
  methods: {
    addMusic() {
      if (this.newMusic === "") return;
      this.musics.push(this.newMusic);
      this.newMusic = "";
      // console.log(this.newMusic);
    }
  }
}
</script>>