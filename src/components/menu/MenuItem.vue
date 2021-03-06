<template>
  <a v-if="to" :href="href" :target="target" :class="classes" @click="handleClick"><slot></slot></a>
  <li v-else="" :class="classes" @click="!disabled && handleActive()"><slot></slot></li>
</template>

<script>
import { oneOf } from '../../utils/assist'
import emitter from '../../mixins/emitter'
export default {
  name: 'vi-menu-item',
  mixins: [emitter],
  props: {
    name: {
      type: [String, Number],
      required: true
    },
    to: {
      type: [Object, String]
    },
    replace: {
      type: Boolean,
      default: false
    },
    disabled: {
      type: Boolean,
      default: false
    },
    target: {
      type: String,
      validator (value) {
        return oneOf(value, ['_blank', '_self', '_parent', '_top'])
      },
      default: '_self'
    }
  },
  data () {
    return {
      active: false
    }
  },
  computed: {
    href () {
      return typeof this.to === 'string' ? this.to : null
    },
    classes () {
      return [
        'vi-menu-item',
        {
          'vi-menu-item-active': this.active,
          'vi-menu-item-disabled': this.disabled
        }
      ]
    }
  },
  mounted () {
    this.$on('update-active', (name) => {
      this.active = this.name === name
    })
  },
  methods: {
    handleClick (event) {
      // 禁用
      if (this.disabled) return event.preventDefault()
      // _blank 原生事件
      if (this.target === '_blank') return
      event.preventDefault()
      this.handleJump(event)
    },
    handleJump (event) {
      if (event.ctrlKey || event.metaKey) {
        window.open(this.to)
      } else if (this.$router) {
        this.replace ? this.$router.replace(this.to) : this.$router.push(this.to)
      } else {
        window.location.href = this.to
      }
      this.handleActive()
    },
    handleActive () {
      this.active = true
      this.bubbling('vi-menu', false, 'menu-item-active', this.name)
    }
  }
}
</script>
