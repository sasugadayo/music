<template>
  <main class="main">
    <button class="musicBtn" @click="musicStart">
      Music
    </button>
    <button class="startBtn" @click="appStart" v-if="isStarted == false">
      Start
    </button>
    <section class="touchZone" v-else></section>
  </main>
</template>

<script>
import Tone from "tone";

export default {
  data() {
    return {
      isStarted: false
    };
  },
  methods: {
    appStart() {
      this.isStarted = true;
    }, // <- 複数のメソッドを置く場合はコンマが必要

    // ====== ここから追加する ======
    musicStart() {
      var synth = new Tone.Synth().toMaster();
      synth.triggerAttackRelease("C4", "8n");
    }
    // ====== ここまで追加する ======
  }
};
</script>

<style>
.main {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.startBtn,
.musicBtn {
  padding: 10px 20px;
}

/* ここから編集 */
.touchZone {
  background: linear-gradient(45deg, rgb(255, 255, 255), rgb(100, 255, 255));
  width: 100%;
  min-width: 100%;
  height: 100vh;
  min-height: 100vh;
}
/* ここまで編集 */
</style>
