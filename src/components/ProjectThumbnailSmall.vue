<!--

filename: ProjectThumbnailSmall.vue
description: Mini thumbnail component for completed projects, for use on dashboard and committee pages

author: Gabe Landau <gll1872@rit.edu>

-->

<template>
  <div class="project_thumbnail_small">
		<div class="project_thumbnail_small_header">Gender Neutral Bathrooms</div>
    <div class="project_thumbnail_small_tag"><span>Student Affairs</span></div>
	</div>
</template>

<script>
export default {
  name: 'project-thumbnail-small',
  data () {
    return {
    }
  },
  sockets: {
  },
  beforeMount () {
  }
}
</script>

<style scoped lang="sass">
  @import '../assets/vars.sass'

  .project_thumbnail_small
    background-color: #fff
    padding: 20px

  .project_thumbnail_small_header
    color: $primary
    font-size: 16pt
    font-weight: 300

  .project_thumbnail_small_tag
    color: #fff
    font-size: 14pt
    font-weight: 300
    margin-top: 50px
    span
      background-color: $primary
      padding: 5px
</style>
