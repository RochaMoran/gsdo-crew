<template>
   <div class="modal">
      <div class="modalHead">
        <span class="modalHeadTitle">{{item.title}}</span>
        <button class="modalHeadButtonClose" @click="closeModal()">
          X
        </button>
      </div>
      <div class="modalBody">
        <img v-if="!item.url" :src="item.img" :alt="item.title">
        <iframe
          v-if="item.url"
          :src="item.url"
          width="100%"
          height="100%"
        ></iframe>
      </div>
    </div>
    <div class="modalBackground" @click="closeModal()"></div>
</template>

<script>
export default {
  name: "ModalWork",
  props: {
    item: {
      url: String,
      title: String,
      img: String
    },
    changeShow: Function
  },
  methods: {
    closeModal() {
      this.changeShow();
    }
  }
};
</script>
