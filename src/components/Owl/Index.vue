<template>
  <div class="owl">
    <div class="ear ear-left"></div>
    <div class="ear ear-right"></div>
    <div :class="['eye', 'eye-left', closeEye ? 'close-eye': '']">
      <div class="pupil"></div>
      <div class="eye-ball"></div>
    </div>
    <div :class="['eye', 'eye-right', closeEye ? 'close-eye': '']">
      <div class="pupil"></div>
      <div class="eye-ball"></div>
    </div>
    <div class="nose"></div>
  </div>
</template>

<script>
export default {
  props: {
    closeEye: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>
.owl {
  position: fixed;
  left: 50%;
  transform: translate(-50%, 0);
  border: 10px solid #05080F;
  border-radius: 50%;
  width: 120px;
  height: 120px;
  top: 20px;
  background-color: #6B5734;
}

.owl::before,
.owl::after {
/*  content: '';
  border: 6px solid #05080F;
  height: 10px;
  bottom: -22px;
  position: absolute;*/
}

.owl::before {
  /*left: 37px;*/
}

.owl::after {
  /*left: 56px;*/
}

.owl .ear {
  position: absolute;
  top: 20px;
  width: 40px;
  height: 12px;
  background-color: #07080A;
}

.owl .ear-left {
  left: -15px;
  border-radius: 0 0 0 90px;
}

.owl .ear-right {
  right: -15px;
  border-radius: 0 0 90px 0;
}

.owl .eye {
  background-color: #F5D62E;
  border: 10px solid #05080F;
  border-radius: 50%;
  width: 60px;
  height: 60px;
  position: absolute;
  transform: translate(0, -50%);
  top: 50%;
}

.owl .eye-right {
  right: -10px;
}

.owl .eye-left {
  left: -10px;
}

.owl .eye .pupil {
  position: absolute;
  height: 30px;
  width: 60px;
  border-radius: 90px 90px 0 0;
  background: #4D391E;
  border: 10px solid #05080F;
  margin-top: -10px;
  margin-left: -10px;
  animation: blink 5s infinite ease forwards;
  transition: all .3s ease;
  z-index: 1;
}
@keyframes blink {
  0%, 98%{
    height: 30px;
    border-radius: 90px 90px 0 0;
  }
  100% {
    height: 60px;
    border-radius: 90px;
  }
}
.owl .close-eye .pupil {
  animation: none;
  height: 60px;
  border-radius: 90px;
}
.owl .eye .eye-ball {
  position: absolute;
  border-radius: 0 0 90px 90px;
  background: #050608;
  top: 15px;
  transform: translate(-50%, 0);
  left: 50%;
  width: 25px;
  height: 12px;
}
/*.owl .eye .pupil:before {
  content: "";
  position: absolute;
  border-radius: 0 0 90px 90px;
  background: #050608;
  top: 15px;
  transform: translate(-50%, 0);
  left: 50%;
  width: 25px;
  height: 12px;
}
*/
.owl .nose {
  position: absolute;
  transform: translate(-50%, -50%);
  left: 50%;
  top: 60%;
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 40px 10px 0 10px;
  border-color: #05080F transparent transparent transparent;
}
</style>