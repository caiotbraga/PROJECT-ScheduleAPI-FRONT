<template>
    <div class="container mt-5">
        <div class="card">
            <div class="card-header">
                <h4>Add User</h4>
            </div>
            <div class="card-body">
                <!-- <ul class="alert alert-warning" v-if="errorList.length > 0">
                    <li class="mb-0 ms-3" v-for="(error, index) in errorList" :key="index">
                        {{ error.message }}
                    </li>
                </ul> -->
                <div class="mb-3">
                    <label for="">Name</label>
                    <input type="text" v-model="model.user.userName" class="form-control" />
                    <span v-if="buttonPressed && !model.user.userName" class="text-danger">Name is required</span>
                </div>
                <div class="mb-3">
                    <label for="">Email</label>
                    <input type="text" v-model="model.user.Email" class="form-control" />
                    <span v-if="buttonPressed && !model.user.email" class="text-danger">Email is required</span>
                </div>
                <div class="mb-3">
                    <label for="">Number</label>
                    <input type="text" v-model="model.user.phoneNumber" class="form-control" />
                    <span v-if="buttonPressed && !model.user.phoneNumber" class="text-danger">Phone Number is required</span>
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
    data() {
        return {
            errorList: [],
            model: {
                user: {
                    userName: '',
                    email: '',
                    phoneNumber: ''
                }
            },
            buttonPressed: false
        }
    },
    methods: {

        saveUser() {
            this.buttonPressed = true;

            if (!this.model.user.userName || !this.model.user.email || !this.model.user.phoneNumber) {
                this.errorList = [{ message: 'All fields are required' }];
                return;
            }

            axios.post('http://localhost:7156/user', this.model.user)
                .then(res => {

                    console.log(res.data)
                    alert("User " + this.model.user.userName + " Created")
                    alert(res.data.message);

                    this.model.user = {
                        userName: '',
                        email: '',
                        phoneNumber: ''
                    }
                })
                .catch(error => {
                    this.errorList = [{ message: 'An error occurred while creating the user' }];
                    console.error(error);
                });

        }
    },
}
</script>