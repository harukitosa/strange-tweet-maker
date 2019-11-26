<template>
    <v-layout>
        <v-flex class="text-center">
            <h2>くしゃみツイート</h2>
            <p>ひらがなの’は’を入力するとはっくしょん、’ひ’をにゅうりょくするとひっくに変換されるよ！
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
            for (var i = 0; i < this.message.length; i++) {
                if(this.message[i] == 'は' || this.message[i] == 'ハ') {
                    str += 'ハックション'
                } else if (this.message[i] == 'ひ' || this.message[i] == '匕'){
                    str+='ひっく'
                } else {
                    str+=this.message[i]
                }                
            }
            return str;
        }
    },
    methods: {
        popUpTweetWindow() {
            const url = `https://twitter.com/intent/tweet?text=${this.reverse}+%20%23変なツイートメーカー&url=https://strange-tweet-maker.com/kushami`
            const option = 'status=1'
            window.open(url, 'twitter', option)
        },
    }
}
</script>
