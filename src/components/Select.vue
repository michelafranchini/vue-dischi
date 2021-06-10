<template>
    <section>
        <label for="genres">Quale genere ti piacerebbe ascoltare?</label>
            <select 
            id="genres" 
            name="genrelist" 
            form="genre"
            v-model="selectGenre"
            @change="$emit('selected', selectGenre)">
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Metal">Metal</option>
                <option value="Jazz">Jazz</option>
                <span>{{selectGenre}}</span>
            </select>
    </section>
</template>

<script>
export default {
    name: "Select", 
    data() {
        return {
            selectGenre: "", 
        }
    }
}
</script>

<style lang="scss" scoped>
    section {
        display: flex;
        justify-content: center;

    }
    label {
        margin: 10px;
        text-transform: uppercase;
        font-weight: bold;
        color: white;
    }
    select {
        margin: 10px; 
        width: 150px; 
    }
</style>