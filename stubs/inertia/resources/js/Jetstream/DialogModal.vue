<template>
  <modal :id="id" :max-width="maxWidth">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title">
          <slot name="title">
          </slot>
        </h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <slot name="content">
        </slot>
      </div>
      <div class="modal-footer">
        <slot name="footer">
        </slot>
      </div>
    </div>
  </modal>
</template>

<script>
  import { defineComponent } from 'vue'
  import Modal from './Modal.vue'

  export default defineComponent({
    components: {
      Modal,
    },

    props: {
      id: {
        type: String,
        required: true
      },
      maxWidth: {
        default: '2xl'
      }
    }
  })
</script>
