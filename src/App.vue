<!--
HACKIFY by Alexander Abraham, 
a.k.a. "Angel Dollface".
Licensed under the MIT license.
-->

<!--
We use the imported
components in order
and render them.
-->
<template>
 <HeadingCog/>
 <ConverterCog/>
 <SpacerCog/>
</template>

<!--
The script for this main "App"
component that imports and registers
the components of our app.
-->
<script>
 import HeadingCog from './components/HeadingCog.vue';
 import ConverterCog from './components/ConverterCog.vue';
 import SpacerCog from './components/SpacerCog.vue';
 export default {
    name: 'App',
    components: {
        HeadingCog,
        ConverterCog,
        SpacerCog
    }
 }
</script>