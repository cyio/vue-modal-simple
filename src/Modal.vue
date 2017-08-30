<template>
  <div class="modal-mask" v-show="show" transition="modal">
    <div class="modal-wrapper" @click.self="close">
      <div class="modal-container">
        <div class="modal-body">
          <slot name="body">default body</slot>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'modal',
  props: {
    title: {
      type: String,
      default: ''
    },
    show: false
  },
  data () {
    return {
    }
  },
  watch: {
    show (newValue) {
      const body = window.document.querySelectorAll('body')[0]
      body.classList.toggle('modal-open')
    }
  },
  methods: {
    close () {
      this.$emit('close')
    }
  },
  mounted () {
  }
}
</script>
<style>

.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, .7);
  display: table;
  transition: opacity .3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 300px;
  margin: 0px auto;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
  transition: all .3s ease;
  font-family: Helvetica, Arial, sans-serif;
  border-radius: .10rem;
  position: relative;
}

.modal-header h3 {
  margin-top: 0;
  color: #42b983;
}

.modal-body {
  background-color: #fff;
  color: #000
}

.modal-default-button {
  width: 0.7rem;
  height: 0.28rem;
  background-color: #e71d36;
  border: none;
  color: #fff;
  border-radius: .05rem;
  font-size: 14px;
}

.modal-enter, .modal-leave {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
.modal-header {
  background: theme;
  height: 30px;
  line-height: 30px;
  color: #fff;
  font-size: 22px;
  padding: 5px 10px;
  display: flex;
  justify-content: center;
  border-bottom: 1px solid gainsboro;
  border-top-left-radius: .10rem;
  border-top-right-radius: .10rem;
}
.modal-header .close {
  position: absolute;
  right: .05rem;
  font-size: 35px;
}
.modal-footer {
  text-align: center;
}
</style>
