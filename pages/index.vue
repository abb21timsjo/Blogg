<template>
 <div>
<div>
  <div class="box">
    <div class="w-1/2 bloggbox text-center text-xl xl:text-7xl lg:text-6xl md:text-5xl sm:text-4xl ">
      Tottenham <br> 
      bloggen
    </div>
    <div class="litlebox1 w-1/4 xl:text-8xl lg:text-7xl md:text-7xl">
      <p class="">
        To<br> Dare <br> Is To <br> Do
      </p>
    </div>
    <div class="litlebox2 w-1/4 pb-1/2">
      
    </div>
  </div> 
  <div class="box relative">
    <div class="arena w-1/2 pb-1/2">
      <img src="https://i2-prod.football.london/incoming/article18458590.ece/ALTERNATES/s1200c/0_GettyImages-1250936278.jpg">
    </div>
    <div class="arena w-1/2 pb-1/2 h-1/2">
    <img src="https://www.linkpicture.com/q/box_1.jpg">
    </div>
    <div class="xl:text-9xl md:text-6xl lg:text-7xl sm:text-4xl bottom-0 COYS">
      Come On You SPURS
    </div>
  </div>
  <div class="box">
    <div class="about-me w-3/4">
      <nuxt-content :document="markdown"></nuxt-content>

   

    </div>
    <div class="Mer w-1/3 text-center">
        <nuxt-link to="/about-us">
          Mer om Tottenham
        </nuxt-link>
        <!-- <button @click="navigate('about-us')">Mer om mig</button> -->
    </div>
  </div>
  <div class="box">
    <div class="w-1/4 fillbox">
    <p class="play absolute text-9xl "> Spelare </p>     
    </div>
    <div class="w-1/4 fillbox"><img src="https://www.linkpicture.com/q/combined-tottenham-memories.png" class="memo w-2/5"></div>
    <div class="w-1/4 fillbox"></div>
    <div class="w-1/4 fillbox1"></div>
  </div>
 

    <div class="box">
      <div class="w-1/2 playerbox1">
        <nuxt-link to="/player-details/2">
          <img class="playersize w-1/2" src="https://resources.premierleague.com/premierleague/photos/players/250x250/p445044.png">
        </nuxt-link>
      </div>
      <div class="w-1/2 playerbox2">
        <nuxt-link to="/player-details/1">
          <img class="playersize w-1/2" src="https://resources.premierleague.com/premierleague/photos/players/250x250/p78830.png">
        </nuxt-link>
      </div>
    </div>
     <div class="box2"> 
      <div class="playername w-1/2 xl:text-7xl md:text-6xl">
      Kulusevski
      </div>
      <div class="playername1 w-1/2 xl:text-7xl md:text-6xl">
        Harry Kane
      </div>
     </div>

      <div class="box">
      <div class="w-1/2 playerbox1">
        <nuxt-link to="/player-details/18">
          <img class="playersize w-1/2" src="https://resources.premierleague.com/premierleague/photos/players/250x250/p37915.png">
        </nuxt-link>
      </div>
      <div class="w-1/2 playerbox3">
         <nuxt-link class="xl:text-9xl lg:text-8xl md:text-8xl text-center" to="/Players">
            Mer spelare
         </nuxt-link>
      </div>
    </div>
     <div class="box2"> 
      <div class="playername w-1/2 xl:text-7xl md:text-6xl">
        Hugo Lloris
      </div>
      <div class="playername1 w-1/2 text-7xl">
        
      </div>
     </div>

       <div class="box2"> 
      <div class="filler w-1/2">
        
      </div>
      <div class="filler w-1/2 border-l-2 border-black">
        
      </div>
     </div>
</div>
 </div>


</template>

<script>
export default {
  async asyncData({$content}) {
    let markdown = await $content('Tottenham').fetch()
    
    return {
      markdown
    }
  }
}

</script>

<style>
.bloggbox {
  background-color: rgb(	185, 140, 241);
  color: black;
  border-style: solid;
  border-color: black;
  box-shadow: 0px 3px 8px #000;
  display: flex;
  justify-content: center;
  align-items: center;
}
.box1 {
  background-color: #7f8364 ;
  border-style: solid;
  border-color: black;
  vertical-align: text-bottom;
  padding-right: 50px;
  box-shadow: 0px 3px 8px #000;
  text-align: end;
}
body {
  font-family: sans-serif;
  background-color: rgb(239,239,239);;
}
.litlebox1 {
  padding-top: 50px;
  background-image: url(https://ak.picdn.net/shutterstock/videos/1072449197/thumb/1.jpg?ip=x480);
  color: white;
  text-align: center;
  box-shadow: 0px 3px 8px #000;
}
.litlebox2 {
  padding-top: 100px;
  background-image: url(https://www.linkpicture.com/q/harry-kane-background.jpg);
  color: white;
  text-align: center;
  box-shadow: 0px 3px 8px #000;
}
 .box {
   display: flex;
	justify-content: center;
 }
 .box2 {
   display: flex;
   justify-content: space-evenly;
   
 }
.arena {
  box-shadow:  0px 3px 8px #000;
  
}
.COYS{
  position: absolute;
  z-index: 2;
	align-items: flex-end;
  display: flex;
  vertical-align: bottom;
  text-align: center;
  color: #efefef;
  
}
.about-me {
  height: 500px;
  background-color: #efefef ;
  padding-top: 30px;
  border-style: solid;
  border-color: #000;
  border-width: 2px;
  overflow: hidden;
  text-overflow: ellipsis;
}
.Mer {
  height: 500px;
  background-color: #efefef ;
  border-style: solid;
  border-color: #000;
  border-bottom-width: 2px;
  border-top-width: 2px;
  border-right-width: 2px;
  width: 600px;
  font-size: 70px;
  padding-top: 150px;
  padding-left: 50px;
}
.bigbox {
  background-color:  #efefef ;
  border-style: solid;
  border-left-width: 2px;
  border-right-width: 2px;
  border-bottom-width: 2px;
  border-color: #000;
  width: 100%;
  height: 1200px;
  align-content: center;
}
.memo {
  justify-content: center;
  position: absolute;
  z-index: 1;
  padding-top: 100px;
}
.fillbox{
  height: 1400px;
  background-color:  #efefef ;
  border-left: 2px solid #000;
  border-bottom: 2px solid #000;
}
.fillbox1 {
  height: 1400px;
  background-color:  #efefef ;
  border-left: 2px solid #000;
  border-bottom: 2px solid #000;
  border-right: 2px solid #000;
  }
  .play {
    padding-top: 1200px ;
  }
  .playername {
    height: 100px;
    background-color: #efefef;
    border-left: 2px solid #000;
    border-bottom: 2px solid #000;
  }
  .playername1 {
    height: 100px;
    background-color: #efefef;
    border-left: 2px solid #000;
    border-bottom: 2px solid #000;
    border-right: 2px solid #000;
  }
  .playerbg {
    background-color: #d7d0cc;
  }
  .playersize {
    width: 900px;
    background-color: #d7d0cc;
    justify-content: center;
    border-color: #efefef;
    border-width: 30px;
    
    
  }
  .playerbox1 {
      border-left: 2px solid #000;
      border-bottom: 2px solid #000;
 
  }
  .playerbox2 {
    border-left: 2px solid #000;
    border-right: 2px solid #000;
  }
  .playerbox3 {
    background-color: #efefef;
    border-left: 2px solid #000;
    border-bottom: 2px solid #000;
    border-right: 2px solid #000;
    display: flex;
    justify-content: center;
	  align-items: center;
  }
  .filler {
     height: 100px;
    background-color: #efefef;
  }
</style>