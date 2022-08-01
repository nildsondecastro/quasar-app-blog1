<template>
  <q-page class="container q-pa-xs">
    <div class="row q-gutter-md">
      <div class="col-xs-12 col-sm-3" v-for="artigo in 10" :key="artigo">
        <q-card class="my-card">
          <q-img src="~assets/quasar-logo-vertical.svg" />

          <q-card-section>

            <div class="row no-wrap items-center">
              <div class="col text-h6 ellipsis">
                Título
              </div>
            </div>

          </q-card-section>

          <q-card-section class="q-pt-none">
            <div class="text-subtitle1">
              resumo
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
  name: 'Posts'
}
</script>
