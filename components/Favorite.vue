<template>
    <div class="favorite">
        <h3>おすすめ</h3>
        <nuxt-link class="link" to="/inspire">リバースツイート</nuxt-link>
        <nuxt-link class="link" to="/fizbuzz">fizzbuzzツイート</nuxt-link>
        <nuxt-link class="link" to="/karepip">彼ピッピツイート</nuxt-link>
    </div>
</template>

<style scoped>
.favorite {
    max-width: 600px;
    width: 100vw;
    margin: auto;
    display: flex;
    flex-flow: column nowrap;
    justify-content: center;
}
h3 {
  margin: 32px auto;
}
.link {
    text-decoration: none;
    margin: auto;
    font-size: 28px;
    color: #dd0201;
}
</style>
