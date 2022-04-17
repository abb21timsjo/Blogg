<template>
<div class="w-1/2 mx-auto text-white text-center">
    <h1 class="text-5xl mb-8 ">{{Tottenham.title}}</h1>
    <nuxt-content :document="Tottenham"></nuxt-content>
</div>
</template>

<script>
export default {
    async asyncData({$content, params}) {
        
        let Tottenham = await $content('Tottenhams/Tottenham'+params.id).fetch()
        console.log(Tottenham)

        return {
            Tottenham
        }
    },
}
</script>