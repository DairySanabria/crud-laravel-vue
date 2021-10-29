<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>

                    <div class="card-body">
                        {{ nombre}}

                        {{ usuarios }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {

        data(){
            return{
                nombre:"hhhhh",
                usuarios:[]
            }
        },

        mounted() {
            console.log('Component mounted.');
               axios.get('/users')
                    .then((res) => {
                        console.log(res.data);
                        this.usuarios = res.data.data;
                    });
        }
    }
</script>
