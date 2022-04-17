<template>
 <div class="mx-24 md:mx-32 lg:mx-40 xl:mx-48 min-h-screen background">
  <div class="flex flex-wrap justify-evenly text-white text-center">
    <div @click="goToPlayer(player.id)" class="w-80 m-12 flex justify-center playerbackground" v-for="player in players" :key="player.id">
      <PlayerListItem :item="player"></PlayerListItem>
    </div>
  </div>
 </div>
</template>

<script>
export default {
  name: 'PlayerPage',
  async asyncData({$content}) {
    let players = await $content('players').without(['body']).fetch()
    return {
      players
    }
  },
  methods: {
    goToPlayer(id) {
      this.$router.push('/player-details/'+id)
    }
  }
}
</script>
<style>
.PlayerMainText {
    font-size: 20px;
}
.PlayerHeader {
    font-size: 35px;
    text-align: center;
    padding-bottom: 15px;
}
.PlayerLH {
    font-size: 30px;
    text-align: center;
    padding-bottom: 5px;
}
.playerbackground {
  background-image: url(https://www.linkpicture.com/q/kaki.jpg);
   box-shadow: 0px 3px 8px #000;
}

</style>