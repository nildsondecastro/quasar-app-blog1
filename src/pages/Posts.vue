<template>
  <q-page class="container q-pa-xs">
    <div class="row q-gutter-md">
      <div class="col-xs-12 col-sm-3" v-for="(post, index) in posts" :key="index">
        <q-card class="my-card">
          <q-img :src="post.jetpack_featured_media_url" />

          <q-card-section>

            <div class="row no-wrap items-center">
              <div class="col text-h6 ellipsis">
                {{ post.title.rendered}}
              </div>
            </div>

          </q-card-section>

          <q-card-section class="q-pt-none">
            <div class="text-subtitle1">
              resumo ...
            </div>
          </q-card-section>

          <q-separator />

          <q-card-actions>
            <q-btn flat round icon="event" />
            <q-btn push color="dark">
              Detalhes
            </q-btn>
          </q-card-actions>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'Posts',
  data () {
    return {
      posts: []
    }
  },
  mounted () {
    this.getPosts()
  },
  methods: {
    getPosts () {
      this.$axios.get('http://viladosilicio.com.br/wp-json/wp/v2/posts')
        .then((res) => {
          this.posts = res.data
          console.log('POSTS', res.data)
        })
        .catch((err) => {
          console.error(err)
        })
    }
  }
}
</script>
