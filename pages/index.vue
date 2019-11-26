<template>
    <v-layout column justify-center align-center>
        <v-flex xs12 sm8 md6>
            <h1 class="pb-5">変なツイートメーカー</h1>
            <p>いつもと違ったツイートをしてみよう！</p>
            <div class="container">
                <nuxt-link class="link" to="/tooth">- トゥースツイート</nuxt-link>
                <nuxt-link class="link" to="/karepip">- 彼ピッピツイート</nuxt-link>
                <nuxt-link class="link" to="/inspire">- リバースツイート</nuxt-link>
                <nuxt-link class="link" to="/bug">- 一つ飛ばしツイート</nuxt-link>
                <nuxt-link class="link" to="/tanuki">- タヌキツイート</nuxt-link>
                <nuxt-link class="link" to="/fizbuzz">- fizzbuzzツイート</nuxt-link>
                <nuxt-link class="link" to="/kushami">- くしゃみツイート</nuxt-link>
            </div>
        </v-flex>
    </v-layout>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
    components: {
        Logo,
        VuetifyLogo
    }
}
</script>

<style lang="css" scoped>
.link {
    text-decoration: none;
    font-size: 28px;
    color: blue;
}

.container {
  display: flex;
  flex-flow: column nowrap;
}
</style>

