<template>
  <form action="">
      <div class="alert modal-card" style="width: auto">
          <header class="modal-card-head">
              <p class="modal-card-title">Are You Sure?</p>
          </header>
          <section class="modal-card-body">
            <p>You're about to close without saving your changes.</p>
          </section>
          <footer class="modal-card-foot">
              <a class="button cancel" type="button" @click="$parent.close()">Go Back</a>
              <a class="button is-casa" type="button" @click="quit()">Proceed</a>
          </footer>
      </div>
  </form>
</template>

<script>
import EventBus from '@/helpers/event-bus';

export default {
  name: 'ConfirmCancel',
  data() {
    return {}
  },
  methods: {
    quit() {
      this.$emit('close');
      EventBus.$emit('cancel');
    }
  }
};
</script>
