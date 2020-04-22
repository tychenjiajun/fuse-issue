<template>
  <div id="app">
    <img
      alt="Vue logo"
      src="./assets/logo.png"
    >
    <input
      v-model="pattern"
      type="text"
    >
    <HelloWorld :msg="msg" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Fuse from 'fuse.js'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data () {
    return {
      pattern: '',
      books: [
        {
          title: "Old Man's War",
          author: {
            firstName: 'John',
            lastName: 'Scalzi'
          }
        },
        {
          title: 'The Lock Artist',
          author: {
            firstName: 'Steve',
            lastName: 'Hamilton'
          }
        },
        {
          title: 'HTML5',
          author: {
            firstName: 'Remy',
            lastName: 'Sharp'
          }
        },
        {
          title: 'Right Ho Jeeves',
          author: {
            firstName: 'P.D',
            lastName: 'Woodhouse'
          }
        },
        {
          title: 'The Code of the Wooster',
          author: {
            firstName: 'P.D',
            lastName: 'Woodhouse'
          }
        },
        {
          title: 'Thank You Jeeves',
          author: {
            firstName: 'P.D',
            lastName: 'Woodhouse'
          }
        },
        {
          title: 'The DaVinci Code',
          author: {
            firstName: 'Dan',
            lastName: 'Brown'
          }
        },
        {
          title: 'Angels & Demons',
          author: {
            firstName: 'Dan',
            lastName: 'Brown'
          }
        },
        {
          title: 'The Silmarillion',
          author: {
            firstName: 'J.R.R',
            lastName: 'Tolkien'
          }
        },
        {
          title: 'Syrup',
          author: {
            firstName: 'Max',
            lastName: 'Barry'
          }
        },
        {
          title: 'The Lost Symbol',
          author: {
            firstName: 'Dan',
            lastName: 'Brown'
          }
        },
        {
          title: 'The Book of Lies',
          author: {
            firstName: 'Brad',
            lastName: 'Meltzer'
          }
        },
        {
          title: 'Lamb',
          author: {
            firstName: 'Christopher',
            lastName: 'Moore'
          }
        },
        {
          title: 'Fool',
          author: {
            firstName: 'Christopher',
            lastName: 'Moore'
          }
        },
        {
          title: 'Incompetence',
          author: {
            firstName: 'Rob',
            lastName: 'Grant'
          }
        },
        {
          title: 'Fat',
          author: {
            firstName: 'Rob',
            lastName: 'Grant'
          }
        },
        {
          title: 'Colony',
          author: {
            firstName: 'Rob',
            lastName: 'Grant'
          }
        },
        {
          title: 'Backwards, Red Dwarf',
          author: {
            firstName: 'Rob',
            lastName: 'Grant'
          }
        },
        {
          title: 'The Grand Design',
          author: {
            firstName: 'Stephen',
            lastName: 'Hawking'
          }
        },
        {
          title: 'The Book of Samson',
          author: {
            firstName: 'David',
            lastName: 'Maine'
          }
        },
        {
          title: 'The Preservationist',
          author: {
            firstName: 'David',
            lastName: 'Maine'
          }
        },
        {
          title: 'Fallen',
          author: {
            firstName: 'David',
            lastName: 'Maine'
          }
        },
        {
          title: 'Monster 1959',
          author: {
            firstName: 'David',
            lastName: 'Maine'
          }
        }
      ]
    }
  },
  computed: {
    msg () {
      const fuse = new Fuse(this.books, {
        // isCaseSensitive: false,
        // findAllMatches: false,
        // includeMatches: false,
        // includeScore: false,
        // useExtendedSearch: false,
        // minMatchCharLength: 1,
        // shouldSort: true,
        // threshold:0.6,
        // location: 0,
        // distance: 100,
        keys: [
          'title',
          'author.firstName'
        ]
      })
      return fuse.search(this.pattern)
    }
  }
  // mounted () {
  //   this.msg = new Fuse(this.books, {
  //     // isCaseSensitive: false,
  //     // findAllMatches: false,
  //     // includeMatches: false,
  //     // includeScore: false,
  //     // useExtendedSearch: false,
  //     // minMatchCharLength: 1,
  //     // shouldSort: true,
  //     // threshold:0.6,
  //     // location: 0,
  //     // distance: 100,
  //     keys: [
  //       'title',
  //       'author.firstName'
  //     ]
  //   }).search(this.pattern)
  // }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
