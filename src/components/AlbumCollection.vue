<template>
  <div>
    <h1
      class="pb-10 text-sm-center text-md-center text-lg-center text-xl-center albumCollection__header fade-transition fade-in"
    >
      Popular Albums
    </h1>
    <album-grid />
    <album-modal />
  </div>
</template>

<script lang="ts">
import AlbumGrid from "@/components/AlbumGrid.vue";
import mixins from "vue-typed-mixins";
import FadeInMixin from "@/mixins/FadeInMixin";
export default mixins(FadeInMixin).extend({
  name: "AlbumCollection",
  components: {
    AlbumGrid,
    AlbumModal: () => import(/* webpackChunkName: "modal" */ "@/components/AlbumModal.vue")
  }
});
</script>

<style lang="scss" scoped>
.albumCollection__header {
  @media #{map-get($display-breakpoints, 'sm-only')} {
    font-size: 2.4em;
  }
  @media #{map-get($display-breakpoints, 'md-only')} {
    font-size: 2.5em;
  }
  @media #{map-get($display-breakpoints, 'lg-and-up')} {
    font-size: 3em;
  }
}
.fade-transition {
  transition: all 0.2s ease-out;
}
.fade-in {
  opacity: 0;
  transform: translateY(50px);
}
</style>
