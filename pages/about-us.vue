<template>
 
<div class="Beige">   
   
    <div class="MerOmMig text-9xl xl:ml-32">
        Tottenham 
    </div>
    <div class="layout">
        <div class="w-1/2 p-16 text-xl">
           
Tottenham Hotspur FC, populärt Tottenham eller Spurs, är en engelsk professionell fotbollsklubb från stadsdelen Tottenham i norra London. 
Klubben grundades 1882. Tottenham har tävlat i Premier League sedan starten 1992. <br> <br>

Hemmamatcherna spelas på den nybyggda arenan Tottenham Hotspur Stadium som invigdes den 3 april 2019. Arenan har en publikkapacitet på 62 850 åskådare.
Tidigare spelade Tottenham på White Hart Lane. <br> <br>

1901 vann Tottenham FA-cupen trots att klubben inte tillhörde The Football League. Ingen annan klubb har lyckats upprepa denna bravad.<br><br>

Tottenham har vunnit den engelska högstaligan två gånger. Den första ligatiteln togs 1950/51. Säsongen 1960/61 var Tottenham först ut på 1900-talet att knipa "dubbeln", det vill säga att vinna den högsta serien i England och FA-cupen samma säsong. Genom att vinna Cupvinnarcupen 1962/63 blev Tottenham det första laget från Storbritannien att ta en stor europeisk cuptitel. Tottenham vann även premiärupplagan av Uefacupen, 1971/72. 2019 spelade Tottenham sin första final i Uefa Champions League. <br> <br>

Tottenhams latinska motto är Audere est Facere ("To Dare Is to Do", "Att våga är att göra"). Klubbemblemet är en tupp som står på en fotboll. Namnet "Hotspur" härstammar från riddaren Harry Hotspur <br> <br>

Spurs huvudrivaler är Londonklubbarna Arsenal och Chelsea. Derbyt mot grannen Arsenal är känt som "The North London Derby". Tottenhams damlag, Tottenham Hotspur FC Women, spelar i FA Women's Super League. <br><br>

Den 6 oktober 1983 blev Tottenham den första klubben i världen att introduceras på börsen. 2021 rankade Forbes Tottenham som den tionde högst värderade fotbollsklubben internationellt med ett uppskattat värde av 2,3 miljarder dollar.



        </div>

        <div class="w-1/2">
            <img src="https://www.linkpicture.com/q/champ.logo.jpg">
        </div>
    </div>
  <div class="buttons"> 
    <div class="flex flex-col text-black text-center w-1/2">
    <nuxt-link class="w-full flex justify-center buttonsin h-32 text-6xl p-8" to="/Players">
            Spelare
         </nuxt-link>
      <div @click="goToTottenham(Tottenham.id)" class="w-full flex justify-center buttonsin h-32 text-6xl p-8" v-for="Tottenham in Tottenhams" :key="Tottenham.id">
        <TottenhamListItem :items="Tottenham"></TottenhamListItem>
      </div>
    </div>
    <div class="w-1/2 lilbox">
        <img src="https://logos-world.net/wp-content/uploads/2020/06/Tottenham-Hotspur-Logo-History.jpg" alt="">
    </div>
  </div> 

</div>



    



</template>

<script>
export default {
  name: 'TottenhamPage',
  async asyncData({$content}) {
    let Tottenhams = await $content('Tottenhams').without(['body']).fetch()
    return {
      Tottenhams
    }
  },
  methods: {
    goToTottenham(id) {
      this.$router.push('/Tottenham-details/'+id)
    }
  }
}




</script>


<style>
.MerOmMig {
    padding-top: 150px;
    
}
.Beige{
    background-color: #efefef;
}
.layout {
    display: flex; 
    border-bottom: #000 2px solid;
}
.background1 {
    background-color: #efefef;
    border-left: #000 2px solid;
    border-right: #000 2px solid;
}
.buttons {
    display: flex;
}
.buttonsin {
    border-bottom: #000 2px solid;
}
.ToTMainText {
    font-size: 20px;
}
.ToTHeader {
    font-size: 35px;
    padding-bottom: 15px;
}
.ToTLH {
    font-size: 30px;
    padding-bottom: 5px;
}
.lilbox {
    border-left: #000 2px solid;
    border-right: #000 2px solid;
    border-bottom: #000 2px solid;
}
</style>