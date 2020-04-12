<template>
<div>
  <NavBar />
  <div class="text-left px-20">
    <svg width="100" height="100" viewBox="0 0 130 130" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path fill-rule="evenodd" clip-rule="evenodd"
        d="M117 19.5C116.999 18.3925 116.716 17.3034 116.176 16.3363C115.637 15.3691 114.859 14.5559 113.916 13.9737C112.974 13.3916 111.899 13.0599 110.792 13.0101C109.686 12.9602 108.585 13.1939 107.594 13.689L56.9595 39H32.5C27.3283 39 22.3684 41.0545 18.7114 44.7114C15.0545 48.3684 13 53.3283 13 58.5C13 63.6717 15.0545 68.6316 18.7114 72.2886C22.3684 75.9456 27.3283 78 32.5 78H34.32L45.8315 112.554C46.2628 113.849 47.0907 114.975 48.1978 115.773C49.305 116.571 50.6352 117 52 117H58.5C60.2239 117 61.8772 116.315 63.0962 115.096C64.3152 113.877 65 112.224 65 110.5V82.017L107.594 103.311C108.585 103.806 109.686 104.04 110.792 103.99C111.899 103.94 112.974 103.608 113.916 103.026C114.859 102.444 115.637 101.631 116.176 100.664C116.716 99.6966 116.999 98.6076 117 97.5V19.5Z"
        fill="#6FD786" />
    </svg>
    <h1 class="text-3xl bree text-green-400">You want to contact us?</h1>
    <p class="opacity-50 mt-4 bree text-green-400">Sure you can do so!</p>
    <p class="opacity-50 bree text-green-400">Just click one of the buttons below and we <br>will bring you to the correct form.</p>
    <div class="flex flex-row mt-10">
      <div class="flex flex-col w-1/4">
        <a v-for="tab in tabs" v-bind:key="tab.id" v-on:click="selectedTab = tab" class="mr-8 my-1 py-4 rounded-lg text-white bg-green-400 text-center font-bold bree hover:opacity-75 opacity-50" :class="{'opacity-100': tab === selectedTab}">{{ tab.title }}</a>
        <p class="mr-8 text-green-400 opacity-50 montserrat-reg mt-6" style="font-size: 0.5rem;">By sending us anything via any contact way you are agreeing to our privacy policy and obviously aknowledge that we might contact you back. </p>
      </div>
      <div class="w-2/4">
          <keep-alive>
          <div v-if="selectedTab" class="w-full h-full m-1 rounded-lg bg-green-400">
              <div v-if="selectedTab" class="px-8 py-6" v-html="selectedTab.content" />
          </div>
          </keep-alive>
      </div>
    </div>
  </div>
  <FooterBar />
</div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import FooterBar from '@/components/FooterBar.vue'

export default {
  data: () => {
    return {
      selectedTab: null,
      tabs: [{
        id: 0,
        title: "Feature / Bug / Issue",
        content: `
          <p class="text-white bree text-xl">Got a feature idea?</p>
          <p class="my-2 text-white montserrat text-xs opacity-50">We are really interested in your idea, please submit it <a class="hover:underline" href="https://github.com/toorusr/app.stfh.chat/issues">here</a> and tag it as an feature request. We will try our best to evaluate and implement the idea. <br>You can also try to implement it yourself. <br>Read <a class="hover:underline" href="https://github.com/toorusr/stfh.chat/blob/master/CONTRIBUTING.md">this</a> document if you want to contribute.</p>
          <p class="mt-1 text-white bree text-xl">It really sucks that people can use the App with a powerbank and you found the solution to that issue?</p>
          <p class="my-2 text-white montserrat text-xs opacity-50">We appreciate all the little performance reports and issues in design or functionality that you have found. <br>Just submit an issue here and we will take a look at it.</p>
          <p class="mt-1 text-white bree text-xl">Found a nasty critical bug or security relevant thing?</p>
          <p class="mt-2 text-white montserrat text-xs opacity-50">Please send a mail to <a class="hover:underline" href="mailto:emergency@max.berlin">emergency@max.berlin</a>.</p>`
      }, {
        id: 1,
        title: "Press stuff",
        content: `
          <div>
            <div class="flex flex-row">
              <a class="p-4 mr-2 flex flex-col hover:opacity-50 bg-green-600 rounded-lg">
                <svg width="62" height="62" viewBox="0 0 62 62" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M12.3997 15.5C10.7554 15.5 9.17837 16.1533 8.01564 17.316C6.85292 18.4787 6.19971 20.0557 6.19971 21.7001V46.5001C6.19971 48.1444 6.85292 49.7214 8.01564 50.8841C9.17837 52.0468 10.7554 52.7001 12.3997 52.7001H49.5997C51.244 52.7001 52.821 52.0468 53.9838 50.8841C55.1465 49.7214 55.7997 48.1444 55.7997 46.5001V21.7001C55.7997 20.0557 55.1465 18.4787 53.9838 17.316C52.821 16.1533 51.244 15.5 49.5997 15.5H44.6831C43.861 15.4999 43.0726 15.1732 42.4914 14.5917L39.0163 11.1166C37.8539 9.95384 36.2771 9.3004 34.6329 9.30005H27.3665C25.7223 9.3004 24.1456 9.95384 22.9831 11.1166L19.508 14.5917C18.9268 15.1732 18.1384 15.4999 17.3163 15.5H12.3997ZM30.9997 43.4001C32.221 43.4001 33.4303 43.1595 34.5587 42.6921C35.687 42.2248 36.7122 41.5397 37.5758 40.6761C38.4394 39.8126 39.1244 38.7873 39.5918 37.659C40.0592 36.5307 40.2997 35.3213 40.2997 34.1001C40.2997 32.8788 40.0592 31.6694 39.5918 30.5411C39.1244 29.4128 38.4394 28.3875 37.5758 27.524C36.7122 26.6604 35.687 25.9753 34.5587 25.508C33.4303 25.0406 32.221 24.8001 30.9997 24.8001C28.5332 24.8001 26.1677 25.7799 24.4236 27.524C22.6795 29.268 21.6997 31.6335 21.6997 34.1001C21.6997 36.5666 22.6795 38.9321 24.4236 40.6761C26.1677 42.4202 28.5332 43.4001 30.9997 43.4001Z" fill="white"/>
                </svg>
                <p class="bree text-white text-center text-xs">Assets</p>
              </a>
              <a class="p-4 flex flex-col hover:opacity-50 bg-green-600 rounded-lg">
                <svg width="59" height="59" viewBox="0 0 59 59" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M11.7998 11.8C11.7998 10.2352 12.4214 8.73456 13.5279 7.62809C14.6343 6.52163 16.135 5.90002 17.6998 5.90002H31.2285C32.7932 5.90036 34.2936 6.52218 35.3998 7.62872L45.4711 17.7C46.5776 18.8062 47.1995 20.3067 47.1998 21.8713V47.2C47.1998 48.7648 46.5782 50.2655 45.4717 51.372C44.3653 52.4784 42.8646 53.1 41.2998 53.1H17.6998C16.135 53.1 14.6343 52.4784 13.5279 51.372C12.4214 50.2655 11.7998 48.7648 11.7998 47.2V11.8Z" fill="white"/>
                </svg>
                <p class="bree text-white text-xs text-center">Statement</p>
              </a>
            </div>
            <p class="mt-3 text-white bree text-xl">You are from the press?</p>
            <p class="mt-2 text-white montserrat text-xs opacity-50">We are sure you got a lot to do in these times.<br>So we collected all of the relevant things for you on this page.<br>You can find our logo and other stuff to use such as example texts there.</p>
            <p class="mt-3 text-white bree text-xl">You got something really important to ask or tell?</p>
            <p class="mt-2 text-white montserrat text-xs opacity-50">Please send a mail to <a class="hover:underline" href="mailto:press@max.berlin">press@max.berlin</a>.</p>
          </div>
        `
      }, {
        id: 2,
        title: "I love what you do",
        content: `
          <div>
            <p class="mt-3 text-white bree text-xl">Awww</p>
            <p class="mt-2 text-white montserrat text-xs opacity-50">We like you too. Haha. Just kidding.<br>It would be lovely if you can tell your friends about us.</p>
            <p class="mt-3 text-white bree text-xl">Just want to share this awesome Product?</p>
            <p class="mt-2 text-white montserrat text-xs opacity-50">If you aren’t interested in the press stuff, you can also look here to see social media complient stuff to share the app and to tell others to stay the fuck home and donate for the wellbeing of the humanity.</p>
            <div class="mt-2 flex flex-row">
              <a class="text-white bree bg-green-600 hover:opacity-50 px-4 py-2 rounded-lg">Share the good stuff</a>
            </div>
            <p class="mt-3 text-white bree text-xl">Want to help in another way?</p>
            <div class="mt-2 flex flex-row">
              <a class="text-white text-xs bree bg-green-600 hover:opacity-50 px-4 py-2 rounded-full">Leave Testimonial</a>
              <a class="text-white text-xs bree bg-green-600 hover:opacity-50 mx-1 px-4 py-2 rounded-full">Add Playstore Review</a>
              <a class="text-white text-xs bree bg-green-600 hover:opacity-50 px-4 py-2 rounded-full">Add Appstore Review</a>
            </div>
          </div>
        `
      }, {
        id: 3,
        title: "I hate what you do",
        content: `
          <div>
            <img class="rounded-lg w-1/2" src="https://media.giphy.com/media/129OnZ9Qn2i0Ew/giphy.gif">
            <p class="mt-3 text-white bree text-xl">Just want to hate and give no constructive critique?</p>
            <p class="mt-2 text-white montserrat text-xs opacity-50">Yeah we understand that, hate is easier than love. <br>Wait no, wtf. <br>Tweet the hate and try to find a twitter handle of us.</p>
          </div>
        `
      }, {
        id: 4,
        title: "Something else",
        content: `
          <p class="mt-3 text-white bree text-xl">Got something else?</p>
          <p class="mt-2 text-white montserrat text-xs opacity-50">You can do that via the form below.<br>Limited to 256 characters, so you don’t send us essays.<br>No one wants essays.</p>
          <form>
            <div class="flex flex-row justify-between w-4/5">
              <input class="pl-3 text-green-400 montserrat text-xs rounded-lg mt-3 mr-1 py-2 px-2" type="text" placeholder="Your name" />
              <input class="pl-3 text-green-400 montserrat text-xs rounded-lg mt-3 py-2 px-2" type="email" placeholder="Your email" />
            </div>
            <div class="relative w-4/5">
              <textarea class="z-0 rounded-lg w-full h-auto mt-2 p-3 text-xs text-green-400"  rows="5" cols="20" maxlength=256 placeholder="Your message"></textarea>
              <div class="hover:opacity-75 absolute z-30 mb-3 mr-3 bottom-0 right-0">
                <button class="z-30">
                  <svg class="z-30" width="43" height="41" viewBox="0 0 43 41" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <rect width="43" height="41" rx="20.5" fill="#6FD786" fill-opacity="0.2"/>
                    <path d="M30.6853 13.3788L27.8307 27.6409C27.6354 28.6575 27.0567 28.8947 26.2543 28.4278L21.9049 25.0167L19.8172 27.1703C19.5722 27.4225 19.3805 27.6334 18.9473 27.6334C18.3828 27.6334 18.4787 27.4112 18.2869 26.8389L16.8064 21.6808L12.5032 20.2614C11.5729 19.9602 11.5658 19.2825 12.7126 18.7968L29.471 11.9368C30.2379 11.5716 30.9765 12.1326 30.6853 13.3788Z" fill="#6FD786"/>
                  </svg>
                </button>
              </div>
            </div>
          </form>
        `
      }],
    }
  },
  name: 'about',
  components: {
    NavBar,
    FooterBar,
  },
  methods: {
    clickTab: function() {
      return this.message.split('').reverse().join('')
    }
  }
}
</script>

<style>
.montserrat-reg {
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
}
</style>
