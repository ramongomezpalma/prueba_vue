<template>
<h1>{{ msg }} de {{ nombre }}</h1>
<p>
    Este es mi primer componente.
</p>
</template>

<script>
export default {
    name: 'ComponentModulo1',
    props: {
        msg: String,
        nombre: String
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
h3 {
    margin: 40px 0 0;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: inline-block;
    margin: 0 10px;
}

a {
    color: #42b983;
}
</style>
