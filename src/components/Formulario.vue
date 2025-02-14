<script>
import { useNoteStore } from '../stores/storeNotas';
import { ref } from "vue";
const store = useNoteStore();
//obj
const note = ref({
    title : "",
    description : "",
    tag : []
})

//var
const newTag = ref("");

const addNote = () =>{
    store.addNote({
        ...note.value
    })
    note.value = {
        title:"",
        discription:"",
        tag:[],
    }
}
const handlersubmit = () =>{
    store.addTag({
        ...note.value
    });
    note.value = {
        tag:"",
    }
}
</script>
//v-model:es para identificar las entradas
<template>
    <h2>Agrega una nueva nota</h2>
    <form @submit.prevent="addNote">
        <div>

            <input placeholder="Agrega un título a tu notita" v-model="note.title" />
        </div>

        <div>
            <input placeholder="Agrega tu nota" v-model="note.description" />
        </div>

        <div>
            <label>
                Elige alguna etiqueta:
            </label>
            <option></option>
        </div>

        <button type="submit">Agregar nota</button>
    </form>
    
    <form @submit.prevent="handlersubmit" >
        <input placeholder="Inserta nueva etiqueta" v-model="newTag">
        //enviar
        <button type="submit"> Agregar etiqueta</button>
    </form>
</template>