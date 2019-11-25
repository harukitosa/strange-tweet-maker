<template>
    <v-layout>
        <v-flex class="text-center">
            <h2>タヌキツイート</h2>
            <p>文字と文字の間に’た’の文字が入るよ。
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
                str += "た"
                str += this.message[i - 1]
            }
            return str;
        }
    },
    methods: {
        popUpTweetWindow() {
            const url = `https://twitter.com/intent/tweet?text=${this.reverse}+%20%23変なツイートメーカー&url=https://strange-tweet-maker.com/tanuki`
            const option = 'status=1'
            window.open(url, 'twitter', option)
        },
    }
}
</script>
