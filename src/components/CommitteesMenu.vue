<!--

filename: CommitteesMenu.vue
description: Component showing the menu of committees with links to the Committee.vue page

author: Gabe Landau <gll1872@rit.edu>

-->

<template>
  <div id="committee_bar" class="committees-menu">
    <ul class="menu">
      <li v-if="loading">Loading...</li>
      <li v-for="(item, index) in committees">
        <router-link v-if="item.enabled == true" :to="{ path: '/committee/' + item.id }">{{item.title}}</router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'committees-menu',
  data () {
    return {
      committees: null,
      loading: true
    }
  },
  sockets: {
    get_committees: function (data) {
      this.committees = data
      this.loading = false
    }
  },
  beforeMount () {
    this.$socket.emit('get_committees')
  }
}
</script>

<style scoped>
a {
  text-decoration: none;
  color: inherit;
}

#committee_bar {
	background-color: #ccc;
	color: #333;
	font-weight: 300;
	text-transform: uppercase;
	padding: 5px 0;
}

#committee_bar ul {
	list-style: none;
	text-align: center;
	padding: 0;
}

#committee_bar ul li {
	padding: 0 15px;
	display: inline;
}
</style>
