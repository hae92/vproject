<template>
  <div class="black-bg" v-if="Modal">
      <div class="white-bg">
        <img :src="Products[SelectedRoom].image" class="room-img">
        <h4>{{Products[SelectedRoom].title}}</h4>
        <p>{{Products[SelectedRoom].content}}</p>
        <button @click="DisplayModel(SelectedRoom, false)">Close</button>
      </div>
    </div>
</template>

<script>
export default {
    name : 'ModalView',
    props : {
        Products : Array,
        SelectedRoom : Number,
        Modal : Boolean,
    },
}
</script>

<style>
.black-bg {
  width : 100%; 
  height : 100%;
  background: rgba(0, 0, 0, 0.5);
  position : fixed;
  padding : 20px;
}
.white-bg {
  width : 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>