<template>
  <div
    class="container-lg h-screen bg-gradient-to-r from-purple-400 via-pink-500 to-red-500 justify-center flex flex-col items-center overflow-auto">
    <div class="">
      <div class="bg-white p-6 rounded-lg flex-col flex items-center" v-if="isSuccessScreenActive">
        <h1 class="font-bold text-4xl text-pink-500">Slam Book Created!</h1>
        <p class="font-bold pb-2 text-2xl">Now , Share Link With Your Friends</p>
      

        <input class="w-full bg-white rounded border border-gray-300 focus:border-indigo-500 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out" type="text" :value="link+name" id="userLink" >
        <button @click="copyLink()" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-full mt-4 ">Copy Link</button>
      </div>


      <div class="text-left text-white " v-else-if="isQuestionScreenActive">
        <h1 class="text-4xl ">Your Friends Will Answer Thease 9 <br> Questions About You</h1>

        <p class="font-bold text-xl">1. Any nickname for {{ name }}?</p>

        <p class="font-bold text-xl">2. Colour which suits {{ name }}?</p>

        <p class="font-bold text-xl">3. One Thing You Like in {{ name }}?</p>

        <p class="font-bold text-xl">4. One Thing You Dislike in {{ name }}?</p>

        <p class="font-bold text-xl">5. Things that are similar in You and {{ name }}?</p>

        <p class="font-bold text-xl">6. Any sweet memories with {{ name }}?</p>

        <p class="font-bold text-xl">7. Your relationship with {{ name }}?</p>

        <p class="font-bold text-xl">8. Any song dedicated fo {{ name }}?</p>

        <p class="font-bold text-xl">9. Can I post Your Answers {{ name }}?</p>


        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-16 m-4 rounded-full"
          @click="isSuccessScreenActive = true">FINISH</button>
      </div>
      <div class="bg-white p-8 rounded-lg text-center flex flex-col" v-else-if="isEnterNameScreenActive">
        <label class="block uppercase tracking-wide text-3xl pb-3text-xs font-bold mb-4" for="grid-password">
          Enter Your Name:
        </label>
        <input id="inline-full-name" v-model="name"
          class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
          type="text" value="Jane Doe" placeholder="Enter Your Name" />
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full"
          @click="isQuestionScreenActive = true">
          NEXT
        </button>
      </div>

      <div v-else class="h-full h-full text-center text-white m-6 flex flex-col items-center w-auto">
        <h1 class="text-6xl font-bold">What Your Friends Think About You?</h1>
        <p class="text-2xl p-6">
          Your Friends Will Give Answers Of Intersting Questions About You
        </p>
   
        <div class="text-center mt-10">
          <button class="border border-white-500 rounded p-3 bg-transparent text-white-500"
            @click="isEnterNameScreenActive = true">
            Create Your Slambook 
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
        name: '',
        isEnterNameScreenActive: false,
        isQuestionScreenActive: false,
        isSuccessScreenActive: false,
        baseUrl: '',
        link: this.baseUrl + 'upload?name=' + this.name
      }
    },
    methods: {
      copyLink() {
        /* Get the text field */
        var copyUrl = document.getElementById("userLink");

        /* Select the text field */
        copyUrl.select();

        /* Copy the text inside the text field */
        document.execCommand("copy");
      }

    },
    mounted() {
      this.baseUrl = window.location.href
      this.link = this.baseUrl + 'upload?name='
    },
  }

</script>
