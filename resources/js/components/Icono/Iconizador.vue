<template>
    <div>
        <!-- Si es Imagen pongo su imagen preview -->
        <div v-if="extImagenesPermitidas.includes(fichero_param.extension)" class="text-center">
            <img style="height:250px;" class="img-thumbnail w-100" :src="'../storage/ficheros/'+root_dir+'/'+fichero_param.nombre_hash" alt="Imagen">
        </div>

        <!-- Si es PDF: Icono PDF -->
        <div v-else-if="fichero_param.extension == 'pdf'" class="text-center">
            <img style="height:250px;" class="img-thumbnail w-100" :src="'../storage/sistema/iconos/pdf.svg'" alt="Icono PDF">
        </div>

        <!-- Si es Doc/Docx: Icono Doc -->
        <div v-else-if="extDocs.includes(fichero_param.extension)" class="text-center">
            <img style="height:250px;" class="img-thumbnail w-100" :src="'../storage/sistema/iconos/doc.jpg'" alt="Icono PDF">
        </div>

        <!-- Si es TXT:  Icono Txt -->
        <div v-else-if="fichero_param.extension == 'txt'" class="text-center">
            <img style="height:250px;" class="img-thumbnail w-100" :src="'../storage/sistema/iconos/txt.png'" alt="Icono TXT">
        </div>

    </div>
</template>

<script>
    export default {
         props:
        {
            'fichero_param':{
                default:{}
            },
            'root_dir':{
                type:String,
                default:''
            }
        },
        data(){
            return{
                fichero:null,
                 extImagenesPermitidas:[
                    'png',
                    'jpg',
                    'jpeg',
                ],
                extDocs:[
                    'docs',
                    'doc',
                    'docx'
                ],
            }
        },
        beforeMount() {
        }
    }
</script>
