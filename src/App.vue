<template>
<div>
    <input type="text" placeholder="todo" v-model="newItem" />
    <button @click="addItem">Dodaj</button>

    <div v-for="item in items" v-bind:key="item.id">
        <h2>{{ item.title }}</h2>
    </div>
</div>
</template>

<script>
export default {
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
                    completed: false,
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
    },
};
</script>
