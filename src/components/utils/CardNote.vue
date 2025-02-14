<script>

</script>

<template>
    <card>
        <div>
            <h3>Nota: </h3>
            <h1>{{ note.title }}</h1>
        </div>
        <div>
            <h5>Descipción: </h5>
            <h4>{{ note.description }}</h4>
        </div>
        <div>
            <div>
                <tags>ETIQUETAS</tags>
            </div>
            <div><button>trash</button><button>edit</button></div>
        </div>

    </card>
</template>