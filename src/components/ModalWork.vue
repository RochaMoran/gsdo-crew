<template>
   <div class="modal">
      <div class="modalHead">
        <span class="modalHeadTitle">{{item.title}}</span>
        <button class="modalHeadButtonClose" @click="closeModal()">
          <img src="@/assets/icons/cancel.png" alt="cancel">
        </button>
      </div>
      <div class="modalBody">
        <template v-if="!item.url">
          <img v-for="(image, i) in item.images" :key="i" :src="image" :alt="item.title" loading="lazy">
        </template>
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
      images: Array
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
