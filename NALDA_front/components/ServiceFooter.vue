<template>
  <div class="Service-footer">
    <ServiceCheck />
    <button class="order-button" @click="MoveCheck">주문하기</button>
  </div>
</template>

<script>
import { mapState, mapMutations } from 'vuex'

export default {
  name: 'ServiceFooter',
  computed: {
    ...mapState('menu', ['selected_foods']),
  },
  methods: {
    ...mapMutations('menu', [
      'SET_CHOICE_FOODS',
      'DELETE_CHOICE_FOODS',
      'CLEAR_CHOICE_FOODS',
      'PLUS_CHOICE_FOODS',
      'MINUS_CHOICE_FOODS',
    ]),
    MoveCheck() {
      if (this.selected_foods.length) {
        const modal = document.getElementsByClassName('check-modal')[0]
        modal.style.display = 'block'
      }
    },
  },
}
</script>

<style scoped>
.Service-footer {
  display: flex;
  flex-direction: column;
  height: 20vh;
  width: 100%;
}
.Service-footer-head {
  display: flex;
  background-color: rgb(69, 169, 200);
  color: white;
  height: 20%;
  align-items: center;
  font-size: 25px;
}
.Service-footer-item-menu {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 30%;
}
.Service-footer-item-num {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 30%;
}
.Service-footer-body {
  overflow: scroll;
}
/* 스크롤 없애기 */
.Service-footer-body::-webkit-scrollbar {
  display: none; /* Chrome, Safari, Opera*/
}
.Service-footer-content {
  display: flex;
  align-items: center;
  padding: 5px;
  font-size: 25px;
}
.Service-footer-content-name {
  width: 30%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.Service-footer-content-num {
  width: 30%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.Service-footer-content button {
  width: 10%;
  border: 0;
  background-color: white;
}
.Service-footer-content-number {
  width: 20%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.Service-footer-content img {
  width: 100%;
  height: 100%;
}
.order-button {
  position: fixed;
  bottom: 7%;
  right: 2%;
  background-color: rgb(69, 169, 200);
  color: white;
  width: 150px;
  height: 60px;
  border-radius: 60px;
  border: none;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 25px;
}
</style>
