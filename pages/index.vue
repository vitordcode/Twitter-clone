<template>
  <div class="flex container h-screen w-full">
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.15.4/css/all.css" integrity="sha384-DyZ88mC6Up2uqS4h/KRgHuoeGwBcD4Ng9SiP4dIRy0EXTlnuz47vAwmeGwVChigm" crossorigin="anonymous">
  <!-- side nade --> 
    <div class="w-1/5 border-r border-lighter px-8 py-2 flex flex-col justify-between">
      <div>
        <button class="h-12 w-12 hover:bg-lightblue text-3xl rounded-full text-blue">
          <i class="fab fa-twitter"></i>
        </button>
        <div>
          <button v-for="tab in tabs" @click="id = tab.id" :key="tab.id" :class="`focus:outline-none hover:text-blue flex items-center py-2 px-4 hover:bg-lightblue rounded-full mr-auto ${id === tab.id ? 'text-blue' : ''}`">
            <i :class="`${ tab.icon } text-2xl mr-4 text-left`"></i>
            <p class="text-lg font-semibold text-left">{{ tab.title }}</p>
          </button>
        </div>
        <button class="text-white bg-blue rounded-full font-semibold focus:outline-none w-full p-3 hover:bg-darkblue">
          Tweet
        </button>
      </div>
      <div class="w-full relative">
        <button class="flex items-center w-full hover:bg-lightblue rounded-full p-2 focus:outline-none">
          <img src="../assets/img/profile.png" class="w-10 h-10 rounded-full border border-lighter" alt="">
          <div class="ml-4">
            <p class="text-sm font-bold leading-light">Steph Dietz</p>
            <p class="text-sm leading-light">@saasyeth</p>
          </div>
          <i class="fas fa-angle-down ml-auto text-lg"></i>
        </button>
        <div class="absolute bottom-0 right-0 w-64 rounded-lg shadow-md border-lightest bg-white">
          <button class="flex items-center w-full hover:bg-lightblue rounded-full p-2 focus:outline-none">
            <img src="../assets/img/profile.png" class="w-10 h-10 rounded-full border border-lighter" alt="">
            <div class="ml-4">
              <p class="text-sm font-bold leading-light">Steph Dietz</p>
              <p class="text-sm leading-light">@saasyeth</p>
            </div>
            <i class="fas fa-angle-down ml-auto text-lg"></i>
          </button>
        </div>
      </div>
    </div>

  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    return {
      tabs: [
        {icon: 'fas fa-home', title: 'Home', id:'home'},
        {icon: 'fas fa-hashtag', title: 'Explore', id: 'explore'},
        {icon: 'far fa-bell', title: 'Notifications', id: 'notifications'},
        {icon: 'far fa-envelope', title: 'Messages', id: 'messages'},
        {icon: 'far fa-bookmark', title: 'Bookmarks', id: 'bookmarks'},
        {icon: 'fas fa-clipboard-list', title: 'Lists', id: 'lists'},
        {icon: 'far fa-user', title: 'Profile', id: 'profile'},
        {icon: 'fas fa-ellipsis-h', title: 'More', id: 'more'}
      ],
      id: 'home',
      dropdown: false,
      trending: [
        {top: 'Trending in TX', title: 'Gigi', bottom: 'Trending with: Rip Gigi'},
        {top: 'Music', title: 'We Won', bottom: '135K Tweets'},
        {top: 'Pop', title: 'Blue Ivy', bottom: '40k tweets'},
        {top: 'Trending in US', title: 'Denim Day', bottom: '40k tweets'},
        {top: 'Trending', title: 'When Beyonce', bottom: '25.4k tweets'},
      ],
      friends: [
        {src: 'elon.jpg', name: 'Elon Musk', handle: '@teslaBoy'},
        {src: 'monk.jpg', name: 'Adrian Monk', handle: '@detective:)'},
        {src: 'kevin.jpg', name: 'Kevin Hart', handle: '@miniRock'}
      ],
      following: [
        {src: 'elon.jpg', name: 'Elon Musk', handle: '@teslaBoy', time: '20 min', tweet: 'Should I just quarantine on mars??', comments: '1,000', retweets: '550', like: '1,000,003'},
        {src: 'kevin.jpg', name: 'Kevin Hart', handle: '@miniRock', time: '55 min', tweet: 'Should me and the rock do another sub-par movie together????', comments: '2,030', retweets: '50', like: '20,003'},
        {src: 'elon.jpg', name: 'Elon Musk', handle: '@teslaBoy', time: '1.4 hr', tweet: 'Haha just made a flame thrower. Shld I sell them?', comments: '100,000', retweets: '1,000,002', like: '5,000,003'},
        {src: 'elon.jpg', name: 'Elon Musk', handle: '@teslaBoy', time: '1.4 hr', tweet: 'Just did something crazyyyyyyy', comments: '100,500', retweets: '1,000,032', like: '5,000,103'}
      ],
      tweets: [
        {content: 'It is so nice outside!'}
      ],
      tweet: {content: ''}
    }
  },
})
</script>