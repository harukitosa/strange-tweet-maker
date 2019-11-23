<template>
    <v-layout>
        <v-flex class="text-center">
            <h2>リバースツイート</h2>
            <p>逆さま言葉で呟けるよ！</p>
            <v-textarea outlined v-model="message" class="mt-12 mb-8"></v-textarea>
            <v-btn class="mb-12" color="#1DA1F2" @click="popUpTweetWindow()">tweetする</v-btn>
            <p>{{reverse}}</p>
        </v-flex>
    </v-layout>
</template>

<script>
export default {
    name: 'home',
    components: {

    },
    data() {
        return {
            message: ''
        }
    },
    computed: {
        reverse: function() {
            return this.message.split('').reverse().join('');
        }
    },
    methods: {
        popUpTweetWindow() {
            const url = `https://twitter.com/intent/tweet?text=${this.reverse}+%20%23変なツイートメーカー&url=https://strange-tweet-maker.netlify.com/inspire`
            const option = 'status=1'
            window.open(url, 'twitter', option)
        },
    }
}
</script>
