<template>
  <!-- ここから編集 -->
  <main class="main">
    <button class="startBtn">Start</button>
  </main>
  <!-- ここまで編集 -->
</template>

<script>
export default {
  // ここから編集
  data() {
    return {
      isStarted: false
    };
  },
  methods: {
    appStart() {
      this.isStarted = true;
    }
  }
  // ここまで編集
};
</script>

<style>
/* ここから編集 */
.main {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.startBtn {
  padding: 10px 20px;
}
/* ここまで編集 */
</style>
