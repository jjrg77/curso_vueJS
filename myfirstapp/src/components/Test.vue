
<template>
    <div><!-- al haber más de una directiva de VUE, lo englobamos todo en un DIV paraque no de error -->  
        <div v-html="myHtml">
        </div>

        <div v-if="showName">
            <p>{{usuario.nombre}}</p>
        </div>
        <div v-else>
            <p>No puedo mostrar nombre</p>
        </div>
        <hr>
        <div>
            <ul>
                <li v-for="tarea in tareas">
                    <p> {{tarea.title}} </p>
                </li>
            </ul>
        </div>
        <div>
            <input type="text" v-model="usuario.nombre">
            <button type="button" v-on:click="saludar(usuario.nombre)">
            CLICA AQUÍ
            </button>
        </div>
    </div>
</template>

<script>
export default {
    /* a través de la función DATA creamos objetos que retornan al template. En este caso TITLE y USER */
    data () {
        return {
            //Creamos objetos que retornamos al TEMPLATE
            title: 'Hola VueJS',
            usuario: {
                nombre: '',
                apellido: ''
            },
            myHtml: '<h3>Hola Vue</h3>',
            showName: false,
            tareas: [
                {title: 'comer'},
                {title: 'cenar'}
            ]
        }
    },

    methods: {
        saludar(name) {
            alert('hola. Bienvenido ' + name)
        }
    }
}
</script>


<style media="screen">

</style>