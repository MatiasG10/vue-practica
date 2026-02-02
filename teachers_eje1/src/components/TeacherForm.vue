<template>
    <section>
        <h3>Añadir Profesores</h3>
        <div><label>Nombre:</label> <input type="text" v-model="teacher.teacherName"></div>
        <div><label>Apellido:</label> <input type="text" v-model="teacher.teacherLastName"></div>
        <div><label>DNI / NIF:</label> <input type="text" v-model="teacher.dni"></div>
        <div><label>Materias:</label> <input type="text" v-model="subject"> <button v-on:click="handleSubject()">
                Agregar</button></div>
        <div>
            <ul>
                <li v-for="(element, index) in teacher.subjects" v-bind:key="index">{{ element }}</li>
            </ul>
        </div>
        <input type="checkbox" v-model="teacher.doc"> Documentacion Entregada
        <button @click="handleAddTeacher()">Agregar</button>
    </section>
    <section>
        <h3>Listado de profesores</h3>
        <table>
            <tr>
                <th>Nombre</th>
                <th>Apellido</th>
                <th>DNI / NIF</th>
                <th>Materias</th>
                <th>Documentacion</th>
            </tr>
            <tr v-for="element in teachers" :key="element.dni">
                <th>{{ element.teacherName }}</th>
                <th>{{ element.teacherLastName }}</th>
                <th>{{ element.dni }}</th>
                <th>
                    <ul>
                        <li v-for="(item, index) in element.subjects" :key="index">{{ item }}</li>
                    </ul>
                </th>
                <th>
                    <span v-if="element.doc">Entregada</span>
                    <span v-else>No Entregada</span>
                </th>
            </tr>
        </table>
    </section>
</template>

<script lang="ts" setup>
import { Ref, ref } from 'vue';

interface ITeacher {
    teacherName: string,
    teacherLastName: string,
    dni: string,
    subjects: Array<string>,
    doc: boolean
}

let teacher: Ref<ITeacher> = ref({
    teacherName: '',
    teacherLastName: '',
    dni: '',
    subjects: [],
    doc: false
})

let teachers: Ref<Array<ITeacher>> = ref([])

let subject: Ref<string> = ref('')

const handleSubject = () => {
    teacher.value.subjects.push(subject.value)
    subject.value = ''
}

const handleAddTeacher = () => {
    teachers.value.push(teacher.value)
    teacher.value = {
        teacherName: '',
        teacherLastName: '',
        dni: '',
        subjects: [],
        doc: false
    }
}

</script>

<style></style>