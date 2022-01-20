<template>
    <section id="uploader">
        <!-- <vs-upload accept=".csv" limit="1" action="https://jsonplaceholder.typicode.com/posts/" @on-success="successUpload"/> -->
        <!-- <vs-input type="file" color="success" label-placeholder="Success" v-model="value2"/> -->
        <!-- <input type="file" id="CV" name="curriculo" placeholder="Currículo" required accept=".csv"> -->
        <!-- <input type="text" -->
        <input type="file" @change="uploadFile" ref="file">
        <br>
        <button @click="submitFile">Upload!</button>
    </section>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            csvFile: {
                Nome: 'Vue.js',
                Csv: '',
            },
        }
    },
    methods:{
        // successUpload(){
        // this.$vs.notify({color:'success',title:'Upload Success',text:'Lorem ipsum dolor sit amet, consectetur'})
        // },

        uploadFile() {
            this.Images = this.$refs.file.files[0];
            console.log("imagens: " + typeof this.Images);
        },
        submitFile() {
            console.log("Entrou no submitFile")

            const formData = new FormData();
            formData.append('file', this.Images);
            const headers = { 
                'Content-Type': 'multipart/form-data',
                'Content-Disposition': 'attachment; filename=file',
                'filename': 'file'
            };

            console.log("formData Criado: " + formData);

            // this.csvFile.Csv = formData;

            console.log("Vamos ver csvFile: " + this.csvFile);

            axios.post('http://127.0.0.1:8000/csvFiles/list',
                formData,
                headers)
                .then((res) => {
                    console.log("Success!");

                    res.data.files; // binary representation of the file
                    res.status; // HTTP status
                });
        }
    }
}
</script>

<style scoped>
#uploader{
    -webkit-box-shadow: 0px -18px 25px -3px rgba(0,0,0,0.3); 
    box-shadow: 0px -18px 25px -3px rgba(0,0,0,0.3);
}
</style>