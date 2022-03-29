<template>
    <div>
      <img :src="product.image" class="room-img">
      <h4>{{product.title}}</h4>
      <p>{{product.price}} 만원</p>
      <!-- <button @click="Increase(index)">허위매물신고</button> <span>신고수 : {{Products[index].count}}</span> -->
    </div>
</template>

<script>
export default {
    name : 'card',
    props : {
        product : Object,
    },
}
</script>

<style>

</style>