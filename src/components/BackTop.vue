<template>
    <div class="back-top" :style="{right,bottom}" @click="backTop" v-show="visible">
        <slot>
            <i class="back-top icon iconfont icon-BackTop" :style="{transform:`scale(${size},${size})`}"></i>
        </slot>
    </div>
</template>
<script>
export default {
  name: 'BackTop',
  props: {
    speed: {
      type: Number,
      default: 15
    },
    right: {
      type: String,
      default: '3%'
    },
    bottom: {
      type: String,
      default: '20%'
    },
    size: {
      type: Number,
      default: 3
    }
  },
  components: {
  },
  data: () => ({
    visible: false
  }),
  methods: {
    backTop () {
      let doc = document.body.scrollTop ? document.body : document.documentElement
      let scrollTop = doc.scrollTop
      const scroll = () => {
        scrollTop = scrollTop + (0 - scrollTop) / this.speed
        if (scrollTop < 1) {
          doc.scrollTop = 0
        } else {
          doc.scrollTop = scrollTop
          window.requestAnimationFrame(scroll)
        }
      }
      scroll()
    },
    scrollListener () {
      // window.scrollY 垂直方向已滚动的像素值
      // window.innerHeight 浏览器可视窗口高度
      this.visible = window.innerHeight < window.scrollY
    }
  },
  created() {
  },
  mounted() {
    window.addEventListener('scroll', this.scrollListener)
  },
  destroyed() {
  },
  activated () {
    window.removeEventListener('scroll', this.scrollListener)
    window.addEventListener('scroll', this.scrollListener)
  },
  deactivated () {
    window.removeEventListener('scroll', this.scrollListener)
  }
}
</script>
<style scoped>
.back-top {
  position: fixed;
  cursor: pointer;
  user-select: none;
  margin-right: 40px;
}

.icon {
  display: flex;
  width: 35px;
  height: 35px;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  user-select: none;
}

.bounceIn {
    animation-duration: 0.75s;
    animation-name: bounceIn;
}
.bounceOut {
    animation-duration: 0.75s;
    animation-name: bounceOut;
}
@keyframes bounceIn {
    20%,
    40%,
    60%,
    80%,
    from,
    to {
        animation-timing-function: cubic-bezier(0.215, 0.61, 0.355, 1);
    }
    0% {
        opacity: 0;
        transform: scale3d(0.3, 0.3, 0.3);
    }
    20% {
        transform: scale3d(1.1, 1.1, 1.1);
    }
    40% {
        transform: scale3d(0.9, 0.9, 0.9);
    }
    60% {
        opacity: 1;
        transform: scale3d(1.03, 1.03, 1.03);
    }
    80% {
        transform: scale3d(0.97, 0.97, 0.97);
    }
    to {
        opacity: 1;
        transform: scale3d(1, 1, 1);
    }
}
@keyframes bounceOut {
    20% {
        transform: scale3d(0.9, 0.9, 0.9);
    }
    50%,
    55% {
        opacity: 1;
        transform: scale3d(1.1, 1.1, 1.1);
    }
    to {
        opacity: 0;
        transform: scale3d(0.3, 0.3, 0.3);
    }
}
</style>