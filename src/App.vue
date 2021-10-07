<template>
  <div
    class="bg-fixed h-screen flex flex-col items-center justify-center"
    style="background-image: url(./src/assets/5566286.jpg)"
  >
    <div class="bg-pink-800 w-3/5 pb-10 h-96 flex items-center justify-center">
      <div class="flex flex-col w-full">
        <h1 class="text-4xl font-normal mb-10 text-white mx-auto mt-4">PROJECT ONE</h1>
        <h2 class="text-4xl font-normal mb-10 text-white mx-auto">STOPWATCH</h2>
        <p class="text-4xl text-white mx-auto mb-10">
          <span>{{ sec }}</span> : <span>{{ tn }}</span>
        </p>
        <div class="mx-auto">
          <button
            class="text-white border-white border-2 px-8 py-6 text-xl mr-3"
            @click="startTimer()"
          >
            Start
          </button>
          <button
            class="text-white border-white border-2 px-8 py-6 text-xl mr-3"
            @click="stopTimer()"
          >
            Stop
          </button>
          <button
            class="text-white border-white border-2 px-8 py-6 text-xl"
            @click="resettime()"
          >
            Reset
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tens: "00",
      seconds: "00",
      sec: 0,
      tn: 0,
    };
  },
  methods: {
    startTimer: function () {
      this.tn = 0;
      this.sec = 0;
      //this.tickTock();
      setInterval(this.tickTock, 10);
    },
    tickTock: function () {
      if (this.tn++ === 100) {
        this.tn = 0;

        this.sec++;
      }
    },
    // startTimer: function (tens, seconds) {
    //   clearInterval(interval);
    //   var interval = setInterval(timer, 10);
    //   function timer() {
    //     this.tens++;

    //     tens = this.tens <= 9 ? "0" + this.tens : this.tens;

    //     if (tens > 99) {
    //       console.log("seconds");
    //       seconds++;
    //       seconds = "0" + seconds;
    //       tens = "0" + 0;
    //     }

    //     if (seconds > 9) {
    //       seconds = seconds;
    //     }
    //     console.log(seconds + ":" + tens);
    //   }
    // },

    // stopTimer: function (interval) {
    //   clearInterval(interval);
    // },
    // resetTime: function (interval) {
    //   clearInterval(interval);
    //   this.tens = "00";
    //   this.seconds = "00";
    // },
    // demo: function () {
    //   this.tens = "ama";
    //   this.seconds = "kofi";
    // },
    stopTimer: function () {
      clearInterval(this.startTimer);
    },
  },
  created() {
    this.startTimer;
  },
};
</script>
