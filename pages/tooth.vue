<template>
    <v-layout>
        <v-flex class="text-center">
            <h2>トゥースツイート</h2>
            <p>ひらがなの「と」を自動で「トゥース」に変換してつぶやきます。</p>
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
            for(var i = 0;i < this.message.length;i++) {
                if(this.message[i] === 'と' || this.message[i] === 'ト') {
                    str += "トゥース"
                } else {
                    str += this.message[i]
                }
            } 
            return str;
        }
    },
    methods: {
        popUpTweetWindow() {
            const url = `https://twitter.com/intent/tweet?text=${this.reverse}+%20%23変なツイートメーカー&url=https://strange-tweet-maker.com/tooth`
            const option = 'status=1'
            window.open(url, 'twitter', option)
        },
    }
}
</script>
