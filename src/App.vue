<template>
 <h1>H4CK1FY</h1>
 <div class="content">
  <input type="text" v-model="inputText" placeholder="Your text goes here."/>
  <p>Result: {{ result }}</p>
  <p>Copied: {{ isCopied }}</p>
  <button @click="convert()">Convert</button>
  <button @click="copy()">Copy</button>
 </div>
 <div class="spacer"></div>
</template>
<script>
import hack from 'hack';
export default {
  // Naming and registering the component.
  name: 'App',
  data() {
    return {
       result: 'Hackified text will appear here.',
       inputText: 'Type your phrase here.',
       isCopied: 'false'
    };
  },
  methods: {
    convert(){
      this.result = hack.hackify(this.inputText);
    },
    copy(){
      navigator.clipboard.writeText(this.result);
      this.isCopied = 'true';
    }
  }
}
</script>
<style lang="scss">
@import 'sass/index.scss';
</style>