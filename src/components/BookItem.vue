<template>
    <div class="book-item" v-bind:class="{'is-complete':book.readed}">
        <p>
        <input type="checkbox" v-on:change="markComplete">    
        {{book.title}}
        <button @click="$emit('del-book', book.id)" class="del">x</button>
        </p>
    </div>
</template>
<script>
export default {
    name: "BooksItem",
    props: ["book"],
    methods: {
        markComplete(){
            this.book.readed = !this.book.readed;
        }
    }
}
</script>

<style scoped>
    .book-item{
        background: white;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .is-complete{
        text-decoration: line-through;
    }

    .del{
        background: darkblue;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>