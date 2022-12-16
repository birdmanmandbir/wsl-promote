<script setup lang="ts">
import "xterm/css/xterm.css";
import { onMounted, ref } from 'vue'
import { Terminal } from 'xterm'
import { FitAddon } from 'xterm-addon-fit';

const terminalRef = ref()
let term: Terminal
onMounted(() => {
  const fitAddon = new FitAddon()
  term = new Terminal({
    fontSize: 14,
    cursorBlink: true,
  });
  term.loadAddon(fitAddon)
  term.open(terminalRef.value);
  term.write('z00617651 $ ')
})
</script>

<template>
  <div id="terminal" ref="terminalRef" class="h-1/2"></div>
</template>

<style>
.xterm-dom-renderer-owner-1 .xterm-rows span {
  width: 5px !important;
}
</style>