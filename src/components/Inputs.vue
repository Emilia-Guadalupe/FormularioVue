<template>
    <input type="text" class="form-control my-2" placeholder="Ingrese Nombre" v-model.trim="tarea.nombre">
    <div class="form-check form-check-inline">
        <input class="form-check-input" type="checkbox" id="inlineCheckbox1" value="javascript" v-model="tarea.categorias">
        <label class="form-check-label" for="inlineCheckbox1">Javascript</label>
    </div>
    <div class="form-check form-check-inline">
        <input class="form-check-input" type="checkbox" id="inlineCheckbox2" value="node" v-model="tarea.categorias">
        <label class="form-check-label" for="inlineCheckbox2">Node.js</label>
    </div>
    <div class="mt-2">
        <div class="form-check form-check-inline">
        <input type="radio" id="radio-1" class="form-check-input" value="urgente" v-model="tarea.estado">
        <label for="radio-1" class="form-check-label">Urgente</label>
        </div>
        <div class="form-check form-check-inline">
        <input type="radio" id="radio-2" class="form-check-input" value="relax" v-model="tarea.estado">
        <label for="radio-2" class="form-check-label">Relax</label>
        </div>
    </div>
    <div class="mt-2">
        <input type="number" class="form-control" v-model.number="tarea.numero">
    </div>

    <button class="btn btn-dark mt-3 btn-block" type="submit" :disabled="bloquearBtn">
        Enviar
    </button>
</template>

<script>
export default {
    props: {
        tarea: Object
    },
    computed: {
    bloquearBtn() {
        return this.tarea.nombre.trim() === "" ? true : false
        }
    }
}
</script>

<style>

</style>