<template>
<div>
    <div class="item">
        <input type="text" placeholder="todo" v-model="newItem" />
        <button @click="addItem">Dodaj</button>
    </div>

    <div class="item" v-bind:class="{ completed: item.completed }" v-for="item in items" v-bind:key="item.id">
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
    },
};
</script>

<style>
.item {
    border: 1px solid #cdcdcd;
    margin: 8px;
    padding: 10px;
}

.completed {
    opacity: 0.5;
}

.completed h2 {
    text-decoration: line-through;
}
</style>
