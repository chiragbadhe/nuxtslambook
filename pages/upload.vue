<template>


  <div class="container-lg h-screen bg-gradient-to-r from-purple-400 via-pink-500 to-red-500 justify-center flex flex-col items-center">
    <div class="font-bold bg-white rounded-lg overflow-auto" v-if="isSuccess">
      <p class="p-4 bg-gray-200 rounded-lg text-xl">Send Screenshot to :{{ senderName }}</p>
      <p class="text-xl p-4 bg-gray-200">My Name :{{ userName }}</p>
      <div class=" pl-6 text-pink-500" v-for="question in questions" :key="question.index">
        Question: {{ question.question }} <br />
        <p class=" text-indigo-700"> Answer: {{ question.answer }} </p>

      </div>
      <div class="p-3 bg-gray-200 rounded-lg text-xl text-center" @click="startAgain()">
          <nuxt-link to="/" class="text-xl p-4 bg-gray-200 text-indigo-700">Create Your Own</nuxt-link>
      </div>
      
    </div>
     

    




    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[8].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">9. Can I post Your Answers</h1>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[8].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="isSuccess = true"> Finish </a>
    </div>




    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[7].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">8. Any song dedicated for {{ senderName }}</h1>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[7].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full mb-2" href="#"
        @click="show(8)"> Next </a>
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="previous(6)"> Previous </a>
    </div>




    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[6].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">7. Your relationship with {{ senderName }}</h1>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[6].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full mb-2" href="#"
        @click="show(7)"> Next </a>
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="previous(5)"> Previous </a>
    </div>




    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[5].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">6. Any sweet memories with {{ senderName }}</h1>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[5].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full mb-2" href="#"
        @click="show(6)"> Next </a>
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="previous(4)"> Previous </a>
    </div>




    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[4].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">5. Things that are similar in You and {{ senderName }}</h1>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[4].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full mb-2" href="#"
        @click="show(5)"> Next </a>
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="previous(3)"> Previous </a>
    </div>




    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[3].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">4. One Thing You Dislike in {{ senderName }}</h1>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[3].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full mb-2" href="#"
        @click="show(4)"> Next </a>
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="previous(2)"> Previous </a>
    </div>





    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[2].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">3. One Thing You Like in {{ senderName }}</h1>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[2].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full mb-2" href="#"
        @click="show(3)"> Next </a>
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="previous(1)"> Previous </a>
    </div>




    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[1].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">2. Colour which suits {{ senderName }}</h1>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[1].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full mb-2" href="#"
        @click="show(2)"> Next </a>
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="previous(0)"> Previous </a>
        
    </div>




    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[0].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">1. Any nickname for {{ senderName }}</h1>
      <h5 v-if="questions[0].error"> {{questions[0].error}} </h5>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[0].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full mb-2" href="#"
        @click="show(1)"> Next </a>
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="startAgain()"> Change Name </a>
    </div>




    <div class="bg-white p-6 rounded-lg text-center flex flex-col" v-else>
      <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <p class="font-bold text-4xl p-5">Enter Your Name</p>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="userName" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full mb-2" href="#"
        @click="show(0)"> Next </a>
    </div>



  </div>
</template>

<script>
  export default {
    data() {
      return {
        senderName: this.$route.query.name,
        userName: '',
        questions: [{
            index: 0,
            question: '1. Any nickname for :' + this.$route.query.name,
            answer: '',
            show: false,
            error: null,
          },

          {
            index: 1,
            question: '2. Colour which suits :' + this.$route.query.name,
            answer: '',
            show: false,
                        error: null,

          },

          {
            index: 2,
            question: '3. One Thing You Like in :' + this.$route.query.name,
            answer: '',
            show: false,
                        error: null,

          },

          {
            index: 3,
            question: '4. One Thing You Dislike in :' + this.$route.query.name,
            answer: '',
            show: false,
                        error: null,

          },

          {
            index: 4,
            question: '5. Things that are similar in You and :' + this.$route.query.name,
            answer: '',
            show: false,
                        error: null,

          },

          {
            index: 5,
            question: '6. Any sweet memories with :' + this.$route.query.name,
            answer: '',
            show: false,
                        error: null,

          },

          {
            index: 6,
            question: '7. Your relationship with :' + this.$route.query.name,
            answer: '',
            show: false,
                        error: null,

          },

          {
            index: 7,
            question: '8. Any song dedicated for :' + this.$route.query.name,
            answer: '',
            show: false,
                        error: null,

          },

          {
            index: 8,
            question: '9. Can I post Your Answers',
            answer: '',
            show: false,
            error: null,

          },


        ],
        isSuccess: false,
      }
    },

    methods: {
      show(index) {
        if(index === 0){
          if(this.userName) {
            this.questions[0].show = true}
            else{
              this.$swal('Enter Name')
            }
        }
        else if(this.questions[index-1].answer) {
            this.questions[index].show = true
        }
        else { 
                this.$swal('Please Answer')
        }
      },

      startAgain(){
        let  i;
        for(i=0; i < this.questions.length; i++) {
        this.questions[i].show = false
        }
      },

      previous(index) {
        this.questions[index + 1].show = false
      }
    },
  }

</script>
