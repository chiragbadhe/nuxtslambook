<template>


  <div class="container-lg h-screen bg-gradient-to-r from-purple-400 via-pink-500 to-red-500 justify-center flex flex-col items-center">
    <div class="font-bold bg-white rounded-lg overflow-auto" v-if="isSuccess">
      <p class="p-4 bg-gray-200 rounded-lg text-xl">Send Screenshot to :{{ senderName }}</p>
      <p class="text-xl p-4 bg-gray-200">My Name :{{ userName }}</p>
      <div class=" pl-6 text-pink-500" v-for="question in questions" :key="question.index">
        Question: {{ question.question }} <br />
        <p class=" text-indigo-700"> Answer: {{ question.answer }} </p>

      </div>
      <div class="font-bold bg-white rounded-lg overflow-auto" >
          <a href="#" class="text-xl p-4 bg-gray-200">create Your Own</a>
      </div>
      
    </div>
     

    




    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[8].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">Question nine</h1>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[8].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="isSuccess = true"> Finish </a>
    </div>




    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[7].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">Question eight</h1>
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
      <h1 class="font-bold text-4xl p-4 pb-">Question seven</h1>
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
      <h1 class="font-bold text-4xl p-4 pb-">Question six</h1>
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
      <h1 class="font-bold text-4xl p-4 pb-">Question five</h1>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[4].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full mb-2" href="#"
        @click="show(6)"> Next </a>
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="previous(3)"> Previous </a>
    </div>




    <div class=" bg-white p-6 text-center m-5 flex flex-col rounded-lg" v-else-if="questions[3].show">
        <p class="bg-gray-200 font-bold pl-4 pr-4 rounded-lg text-2xl">Sent to you by :{{ senderName }}</p>
      <h1 class="font-bold text-4xl p-4 pb-">Question four</h1>
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
      <h1 class="font-bold text-4xl p-4 pb-">Question three</h1>
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
      <h1 class="font-bold text-4xl p-4 pb-">Question two</h1>
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
      <h1 class="font-bold text-4xl p-4 pb-">Question One</h1>
      <input
        class="bg-white rounded-lg border border-gray-400 focus:outline-none focus:border-indigo-500 text-base px-4 py-2 mb-4"
        v-model="questions[0].answer" placeholder="Enter Name" />
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full mb-2" href="#"
        @click="show(1)"> Next </a>
      <a class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-8 rounded-full" href="#"
        @click="previous(0)"> Previous </a>
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
            question: '1. Any nickname for' + this.senderName,
            answer: '',
            show: false,
          },

          {
            index: 1,
            question: 'Hello 1',
            answer: '',
            show: false,
          },

          {
            index: 2,
            question: 'Hello 2',
            answer: '',
            show: false,
          },

          {
            index: 3,
            question: 'Hello 3',
            answer: '',
            show: false,
          },

          {
            index: 4,
            question: 'Hello 4',
            answer: '',
            show: false,
          },

          {
            index: 5,
            question: 'Hello 5',
            answer: '',
            show: false,
          },

          {
            index: 6,
            question: 'Hello 6',
            answer: '',
            show: false,
          },

          {
            index: 7,
            question: 'Hello 7',
            answer: '',
            show: false,
          },

          {
            index: 8,
            question: 'Hello 8',
            answer: '',
            show: false,
          },


        ],
        isSuccess: false,
      }
    },

    methods: {
      show(index) {
        console.log(index)
        console.log(this.questions[index + 1])
        this.questions[index].show = true
      },

      previous(index) {
        this.questions[index + 1].show = false
      }
    },
  }

</script>
