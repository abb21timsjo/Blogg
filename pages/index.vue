<template>
<div class="">
  <div style="text-align: center;">
    <nuxt-content :document="markdown"></nuxt-content> 
  </div>
  <div class="main">
  <span class="border">  </span>
  <img src="https://www.linkpicture.com/q/harry-kane-chant.png" class="kane">
  <img src="https://imgresizer.eurosport.com/unsafe/1200x0/filters:format(jpeg)/origin-imgresizer.eurosport.com/2019/04/03/2557813-53054975-2560-1440.jpg" class="stadium">
  <span class="border">  </span>
  </div>
</div>


</template>

<script>
export default {
  async asyncData({$content}) {
    let markdown = await $content('Harry').fetch()
    
    return {
      markdown
    }
  }
}

</script>

<style>
body {
  background: linear-gradient(90deg, rgba(0,0,0,1) 0%, rgba(48,48,54,1) 100%, rgba(0,0,0,1) 100%);
  color: white;
}
.Harry  {
  background-color:antiquewhite;
  display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	justify-content: space-around;
	align-items: center;
	align-content: space-around;
  color: black;
  font-size: 80px;

}
.kane {
  border-style: solid;
  border-color: black;
  height: 300px;
  align-items: baseline;
}
.border {
  background-color: rgb(252, 245, 229);
  padding-top: 380px;
  padding-right: 40px;
  padding-left:40px;
  justify-content: flex-start;
  border-style: solid;
  border-color: black;
}
.main {
  height: 400px;
}
</style>