`<template>

  <div class="container">

    <div class="block" :class="{ animate: animatedBlock }"></div>

    <button @click="animateBlock">Animate</button>

  </div>

  <div class="container">

    <transition

      :css="false"

      @before-enter="beforeEnter"

      @enter="enter"

      @after-enter="afterEnter"

      @before-leave="beforeLeave"

      @leave="leave"

      @after-leave="afterLeave"

      @enter-cancelled="enterCancelled"

      @leave-cancelled="leaveCancelled"

    >

      <p v-if="paraIsVisible">

        This is a paragraph! Only visible when you click

      </p>

    </transition>

    <button @click="toggleParagraph">Toggle Paragraph</button>

  </div>

  <div class="container">

    <transition name="fade-button" mode="out-in">

      <button @click="showUsers" v-if="!usersAreVisible">Show Users</button>

      <button @click="hideUsers" v-else>Hide Users</button>

    </transition>

  </div>

  <base-modal @close="hideDialog" :open="dialogIsVisible">

    <p>This is a test dialog!</p>

    <button @click="hideDialog">Close it!</button>

  </base-modal>

  <div class="container">

    <button @click="showDialog">Show Dialog</button>

  </div>

</template>

  

<script>

export default {

  data() {

    return {

      animatedBlock: false,

      dialogIsVisible: false,

      paraIsVisible: false,

      usersAreVisible: false,

      enterInterval: null,

      leaveInterval: null,

    };

  },

  methods: {

    showDialog() {

      this.dialogIsVisible = true;

    },

    hideDialog() {

      this.dialogIsVisible = false;

    },

    animateBlock() {

      console.log('animateBlock');

      this.animatedBlock = !this.animatedBlock;

    },

    toggleParagraph() {

      this.paraIsVisible = !this.paraIsVisible;

    },

    showUsers() {

      this.usersAreVisible = true;

    },

    hideUsers() {

      this.usersAreVisible = false;

    },

    enterCancelled(el) {

      console.log('enterCancelled');

      console.log(el);

      clearInterval(this.enterInterval);

    },

    leaveCancelled(el) {

      console.log('leaveCancelled');

      console.log(el);

      clearInterval(this.leaveInterval);

    },

    beforeEnter(el) {

      console.log('beforeEnter');

      console.log(el);

      el.style.opacity = 0;

    },

    enter(el, done) {

      console.log('enter');

      console.log(el);

      let round = 1;

      this.enterInterval = setInterval(() => {

        el.style.opacity = round * 0.05;

        round++;

        if (round > 20) {

          clearInterval(this.enterInterval);

          done();

        }

      }, 20);

    },

    afterEnter(el) {

      console.log('afterEnter');

      console.log(el);

    },

    beforeLeave(el) {

      console.log('beforeLeave');

      console.log(el);

    },

    leave(el, done) {

      console.log('leave');

      console.log(el);

      let round = 20;

      this.leaveInterval = setInterval(() => {

        el.style.opacity = round * 0.05;

        round--;

        if (round === 0) {

          clearInterval(this.leaveInterval);

          done();

        }

      }, 20);

    },

    afterLeave(el) {

      console.log('afterLeave');

      console.log(el);

    },

  },

};

</script>`