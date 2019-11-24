<template>
    <v-layout>
        <v-flex class="text-center">
            <h2>fizzbuzzツイート</h2>
            <p>3の倍数のもじがfizz、5の倍数の文字がbuzzに変換されるよ！
            </p>
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
            var str = '';
            for (var i = 1; i <= this.message.length; i++) {
                if (i != 0 && i % 3 == 0 && i % 15 != 0) {
                    str += "fizz"
                } else if (i != 0 && i % 5 == 0 && i % 15 != 0) {
                    str += "buzz"
                } else if (i != 0 && i % 15 == 0) {
                    str += "fizzbuzz"
                } else {
                    str += this.message[i-1]
                }
            }
            return str;
        }
    },
    methods: {
        popUpTweetWindow() {
            const url = `https://twitter.com/intent/tweet?text=${this.reverse}+%20%23変なツイートメーカー&url=https://strange-tweet-maker.com/fizbuzz`
            const option = 'status=1'
            window.open(url, 'twitter', option)
        },
    }
}
</script>
