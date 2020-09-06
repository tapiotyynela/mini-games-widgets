<template>
    <div>
        <h2>NamePicker</h2>
        <form @submit="addName">
            <input type="text" v-model="name" name="name" placeholder="Add name">
            <input class="btn" type="submit" value="Lisää">
        </form>
        <Names v-bind:names="names" v-on:del-name="deleteName" />
        <button class="btn" @click="pickName">Arvo nimi</button>
        <p>{{  }}</p>
    </div>
</template>

<script>
import Names from './Names'
import { uuid } from 'vue-uuid'

export default {
    name: "NamePicker",
    components: {
        Names
    },
    data() {
        return {
            names: [],
        }
    },
    methods: {
        addName(e) {
            e.preventDefault();
            const newName = {
                id: uuid.v4(),
                name: this.name
            }
            this.$emit('add-name', newName)
            this.names = [...this.names, newName]
            this.name = ''

        },
        deleteName(id) {
            this.names = this.names.filter(name => name.id !== id)
        },
        pickName() {
            const nameIds = this.names.map(name => name.id)
            const nameId = nameIds[Math.floor(Math.random() * nameIds.length)]
            this.names = this.names.filter(name => name.id === nameId);
        }
    }
}
</script>

<style scoped>
    .btn {
        color: #ff8484;
        background: white;
        border-radius: 10%;
        font-family: Arial, Helvetica, sans-serif;
        border: none;
        cursor: pointer;
    }
    .btn:hover {
        background: grey;
    }
    input {
        margin-bottom: 10px;
        margin-right: 10px;
    }
</style>