<template>
<div>
    <div class="item">
        <input type="text" placeholder="todo" v-model="newItem" />
        <button @click="addItem">Dodaj</button>
    </div>

    <TodoItem :item="item" v-for="item in items" :key="item.id" @remove-clicked="removeItem" />
</div>
</template>

<script>
// import TodoItem from "./TodoItem";

export default {
    components: {
        TodoItem,
    },
    data() {
        return {
            newItem: "",
            items: [{
                    id: 1,
                    title: "Zrobic zakupy",
                    completed: false,
                },
                {
                    id: 2,
                    title: "Nagrać film",
                    completed: true,
                },
            ],
        };
    },
    methods: {
        addItem() {
            this.items.push({
                id: 3,
                title: this.newItem,
                completed: false,
            });
            this.newItem = "";
        },
        removeItem(id) {
            const index = this.items.findIndex((el) => el.id === id);
            this.items[index].completed = true;
        },
    },
};
</script>
