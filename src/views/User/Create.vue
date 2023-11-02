<template>
    <div class="container mt-5">
        <div class="card">
            <div class="card-header">
                <h4>Add User</h4>
            </div>
            <div class="card-body">
                <div class="mb-3">
                    <label for="">Name</label>
                    <input type="text" v-model="model.user.userName" class="form-control" />
                </div>
                <div class="mb-3">
                    <label for="">Email</label>
                    <input type="text" v-model="model.user.Email" class="form-control" />
                </div>
                <div class="mb-3">
                    <label for="">Number</label>
                    <input type="text" v-model="model.user.phoneNumber" class="form-control" />
                </div>
                <div class="mb-3">
                    <button type="button" @click="saveUser" class="btn btn-primary">Save</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'userCreate',
    data(){
        return {
            model: {
                user: {
                    userName: '',
                    email: '',
                    phoneNumber: ''
                }
                
            }
        }
    },
    methods: {

        saveUser(){

            axios.post('http://localhost:7156/user', this.model.user)
            .then(res => {
                console.log(res.data)
                alert(res.data.message)

                this.mode.user = {
                    userName: '',
                    email: '',
                    phoneNumber: ''
                }
            })
            .catch(funcion (error) ,{
                
            });
        } 
    },
}
</script>