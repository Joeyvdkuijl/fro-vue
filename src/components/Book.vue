<template>
    <div>
        <div v-bind:key="book.id" v-for="book in books">
            <BookItem v-bind:book="book" v-on:del-book="$emit('del-book', book.id)" />
        </div>
    </div>
</template>

<script>
import BookItem from './BookItem.vue';
export default {
    name: "Books",
    components: {
        BookItem
    },
    props: ["books"]
}
</script>

<style  scoped>

</style>