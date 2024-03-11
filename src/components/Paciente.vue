<script setup>

    import { ref, reactive } from 'vue';

    defineProps({
        paciente: {
            type: Object,
            required: true
        }
    })

    defineEmits(['actualizar-paciente', 'eliminar-paciente'])
</script>

<template>
    <div class="mx-5 my-10 bg-white shadow-md px-5 py-10 rounded-xl">
        <p class="font-bold mb-3 text-gray-700 uppercase">ID:
            <span class="font-normal normal-case">
                {{ paciente.id }}
            </span>
        </p>

        <p class="font-bold mb-3 text-gray-700 uppercase break-words">Nombre:
            <span class="font-normal normal-case">
                {{ paciente.nombre }}
            </span>
        </p>

        <p class="font-bold mb-3 text-gray-700 uppercase break-words">Propietario: 
            <span class="font-normal normal-case">
                {{ paciente.propietario }}
            </span>
        </p>

        <p class="font-bold mb-3 text-gray-700 uppercase break-words">Email: 
            <span class="font-normal normal-case">
                {{ paciente.email }}
            </span>
        </p>

        <p class="font-bold mb-3 text-gray-700 uppercase break-words">Fecha Alta:
            <span class="font-normal normal-case">
                {{ paciente.alta }}
            </span>
        </p>

        <p class="font-bold mb-3 text-gray-700 uppercase break-words">Síntomas:
            <span class="font-normal normal-case">
                {{ paciente.sintomas }}
            </span>
        </p>

        <div class="grid md:grid-cols-2  gap-5 mt-10 ">
            <button 
                type="button"
                class="block w-full py-2 px-10 bg-indigo-600 hover:bg-indigo-700 text-white font-bold uppercase rounded-lg"
                @click="$emit('actualizar-paciente', paciente.id)"
            >Editar</button>

            <button 
                type="button"
                class="block w-full py-2 px-10 bg-red-600 hover:bg-red-700 text-white font-bold uppercase rounded-lg"
                @click="$emit('eliminar-paciente', paciente.id)"
            >Eliminar</button>
        </div>
    </div>
</template>