<template>
    <section>
        <label for="genres">Quale genere ti piacerebbe ascoltare?</label>
            <select 
            id="genres" 
            name="genrelist" 
            form="genre"
            v-model="selectGenre"
            @change="$emit('selected', selectGenre)">
                <option value="">Seleziona un genere</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Metal">Metal</option>
                <option value="Jazz">Jazz</option>
            </select>

            <label for="author">Quale artista cerchi?</label>
            <select 
            id="author" 
            name="authorlist" 
            form="artist"
            v-model="selectGenre"
            @change="$emit('selected', selectGenre)">
                <option value="">Seleziona un artista</option>
                <option value="Bon Jovi">Bon Jovi</option>
                <option value="Queen">Queen</option>
                <option value="Sting">Sting</option>
                <option value="Steve Gadd Band">Steve Gadd Band</option>
                <option value="Iron Maiden">Iron Maiden</option>
                <option value="Eric Clapton">Eric Clapton</option>
                <option value="Deep Purple">Deep Purple</option>
                <option value="Metallica">Metallica</option>
                <option value="Dave Weckl">Dave Weckl</option>
                <option value="Michael Jacjson">Michael Jacjson</option>
            </select>
    </section>
</template>

<script>
export default {
    name: "Select", 
    data() {
        return {
            selectGenre: "", 
            selectArtist:""
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