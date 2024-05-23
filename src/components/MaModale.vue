<script setup>
import { ref } from "vue";
import {onClickOutside} from '@vueuse/core'

const props = defineProps({
  isOpen: Boolean,
  currentProject: Object,
});
const emit = defineEmits(["modal-close"]);
const target = ref(null)
onClickOutside(target, ()=>emit('modal-close'))

</script>
<template>
  <div v-if="isOpen" class="modal-mask">
    <div class="modal-wrapper">
      <div class="modal-container" ref="target">
        <div class="modal-title">
          <slot name="title"> {{ currentProject.title }} </slot>
        </div>
        <div class="modal-body">
          <slot name="content">
            <a :href="currentProject.link" target="_blank">
                <img :src="`/src/assets/${currentProject.image}.png`" :alt="`${currentProject.image}`">
            </a>            
            <p v-if="currentProject.desc">Langage(s) utilisé(s): {{ currentProject.desc }}</p>
            <p>{{ currentProject.date }}</p>
          </slot>
        </div>
        <div class="modal-footer">
          <slot name="footer">
            <div>
              <button @click.stop="emit('modal-close')">Fermer</button>
            </div>
          </slot>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.modal-title{
    display: flex;
    justify-content: center;
    color:rgb(14, 88, 14);
    font-weight: 700;
}
.modal-mask {
    position: fixed;
    z-index: 102;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.2);
    color:black;
}

.modal-container {
    width: 400px;
    margin: 150px auto;
    margin-bottom: 20px;
    padding: 20px 30px;
    text-align: center;
    background-color: #eeeded;
    border-radius: 2px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
    border-radius: 3%;
}

.modal-header{
    color: #010440;
}

button {
    display: block;
    width: fit-content;
    margin: auto;
    padding: .5rem;
    color: #010440;
    background-color: hsla(160, 100%, 37%, 1);
}
img {
    width: 220px;
    height: 330px;
    margin: auto;
    object-fit:cover;
}
</style>