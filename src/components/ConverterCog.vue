<!--
HACKIFY by Alexander Abraham, 
a.k.a. "Angel Dollface".
Licensed under the MIT license.
-->

<!--
This component takes input
from the user and saves it
in the "inputText" Vue
variable. This variable is
converted and then saved in
the "result" variable.
-->
<template>
 <div class="content">
  <!--
  The input field where the 
  user enters the desired phrase.
  -->
  <input type="text" v-model="inputText" placeholder="Your text goes here."/>

  <!--
  This element echoes the converted
  result.
  -->
  <p>Result: {{ result }}</p>

  <!--
  This element echoes whether
  the result has been copied.
  -->
  <p>Copied: {{ isCopied }}</p>

  <!--
  The button that triggers a 
  conversion via
  the "convert" function.
  -->
  <button @click="convert()">Convert</button>

  <!--
  The button that copies
  the text into the clipboard
  via the "copy" function.
  -->
  <button @click="copy()">Copy</button>
 </div>
</template>

<!--
We define the Javascript
for this component.
-->
<script>
 // We import all the APIs
 // that the "hack" package
 // provides.
 import hack from 'hack';

 // We define the component
 // and modularize it.
 export default {
    name: 'ConverterCog',

    // We define the mutable
    // data in this component.
    data() {
        return {
            result: 'Hackified text will appear here.',
            inputText: 'Type your phrase here.',
            isCopied: 'false'
        };
    },

    // We define the methods that
    // the component has.
    methods: {

        // This function takes the "inputText" variable,
        // converts it, and stores it in the "result" variable.
        convert(){
            this.result = hack.hackify(this.inputText);
        },

        // This function takes the "result" variable,
        // and copies it into the system clipboard.
        copy(){
            navigator.clipboard.writeText(this.result);
            this.isCopied = 'true';
        }
    }
 }
</script>