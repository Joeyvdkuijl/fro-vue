<template>
  <div id="app">
    <Header />
    <AddBooks />
    <Books v-bind:books="book" v-on:del-book="deleteBook" />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Books from './components/Book';
import AddBooks from './components/AddBooks';
import Header from './components/layout/header';
export default {
  name: 'App',
  components: {
    Header,
    Books,
    AddBooks
  },
  data() {
    return{
      book: [
              {
        id: 1,
        title: "Pirates of the carribean",
        readed: false
      },
              {
          id: 2,
        title: "Harry Potter",
        readed: false
      },
              {
          id: 3,
        title: "The old republic",
        readed: false
      }
      ]
    }
  },
  methods: {
    deleteBook(id) {
      this.books = this.books.filter(book => book.id !== id);
    }
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn{
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover{
  background: #666;
}
</style>
