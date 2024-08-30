<template>
    <select class="form-control" v-model="selected" :required @change="changeLocation">
        <option :selected>Nivel de interes</option>
        <option v-for="option in options" v-bind:value="option.id" >{{ option.name }}</option>
    </select>

    <input type="text" v-for="option in learn_options"> {{ option.name }}
</template>

<script>
    //https://vuejs.org/examples/#simple-component
    export default {
        data() {
            return {
                select_option: '',
                options: {'name': 'Preaparatoria', 'name': 'Licenciatura', 'name': 'Posgrado'},
                learn_options: '',
            }
        },

        methods: {
            selected() {
                if (this.select_option == 'Licenciatura') {
                    this.learn_options = {name: 'Lic. Derecho', name: 'Lic. Finanzas'};
                }

                if (this.select_option == 'Posgrado') {
                    this.learn_options = {name: 'Adm. Empresas', name: 'Direccion de proyectos'};
                }

                return;
        }
    }
</script>