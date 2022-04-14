<template>
<div class="w-1/2 mx-auto text-white text-center">
    <div class="flex justify-center"><img :src="player.image" /></div>
    <h1 class="text-5xl mb-8 ">{{player.title}}</h1>
    <p class="mb-8 text-4xl">{{player.description}}</p>
    <nuxt-content :document="player"></nuxt-content>
</div>
</template>
<script>
export default {
    async asyncData({$content, params}) {
        
        let player = await $content('players/player'+params.id).fetch()
        console.log(player)

        return {
            player
        }
    },
}
</script>