<template>
  <div class="screen black">
    <v-container class="">
      <div id="title" class="text-center mt-5">Green text typer</div>
      <div id="subtitle" class="text-center">your mindfulness online typer</div>
      <!-- <span class="white--text">{{typedText}}</span> -->
      <v-container class="">
        <v-textarea
          v-model="typedText"
          color="green"
          background-color="black"
          class="mt-12 mx-12 px-12 blue--text"
          name="input-7-4"
          rows="100"
         ></v-textarea>
      </v-container>

    </v-container>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data: () => ({
      typedText: 'start typing...'
    }),
  }
</script>

<style>
.screen {
  height: 10000px;
  font-family: 'Source Code Pro', monospace !important;
  color: #3ab508;
}

#title {
  font-size: 2rem;
  color: #3ab508;
  text-shadow: 2px 2px 5px #3ab508;
}

#subtitle {
  font-size: .8rem;
  color: #3ab508;
}

#input-15 {
  color: #3ab508;
}
</style>
