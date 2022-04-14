<template>
  <div class="flex flex-wrap justify-center text-white text-center ">
    <div @click="goToPlayer(player.id)" class="w-80 m-4 flex justify-center" v-for="player in players" :key="player.id">
      <PlayerListItem :item="player"></PlayerListItem>
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

</style>