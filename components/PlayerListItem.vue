<template>
<div>
    <img :src="item.image" alt="player image" class="h-80 w-64 object-cover" >
    <h3>{{item.title}}</h3>
    <p>{{item.description}}</p>
</div>
</template>

<script>
export default {
    props:['item'],
    data() {
        return {

        }
    }
}
</script>