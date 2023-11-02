<template>
    <div class="container mt-5">
        <div class="card">
            <div class="card-header">
                <h4>Edit User</h4>
            </div>
            <div class="card-body">
                <div class="mb-3">
                    <label for="">Name</label>
                    <input type="text" v-model="model.user.userName" class="form-control" />
                    <span v-if="buttonPressed && !model.user.userName" class="text-danger">Name is required</span>
                </div>
                <div class="mb-3">
                    <label for="">Email</label>
                    <input type="text" v-model="model.user.email" class="form-control" />
                    <span v-if="buttonPressed && !model.user.email" class="text-danger">Email is required</span>
                </div>
                <div class="mb-3">
                    <label for="">Number</label>
                    <input type="text" v-model="model.user.phoneNumber" class="form-control" />
                    <span v-if="buttonPressed && !model.user.phoneNumber" class="text-danger">Phone Number is
                        required</span>
                </div>
                <div class="mb-3">
                    <button type="button" @click="updateUser" class="btn btn-primary">Update</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'userEdit',
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
    mounted() {
        this.getUserData(this.$route.params.id)

    },
    methods: {

        getUserData(userId) {
            axios.get(`http://localhost:7156/users/edit/${userId}`)
                .then(res => {
                    this.model.user = res.data
                })
                .catch(error => {
                    this.$router.replace('/users');
                    alert('User not found');
                });;
        },

        updateUser(userId) {
            this.buttonPressed = true;

            const userUpdateData = {
                userName: this.model.user.userName,
                email: this.model.user.email,
                phoneNumber: this.model.user.phoneNumber
            };

            axios.put(`http://localhost:7156/user/${this.$route.params.id}`, userUpdateData)
                .then(res => {
                    alert("User " + this.model.user.userName + " sucessfully updated")
                    this.buttonPressed = false;
                    this.$router.replace('/users');
                })
                .catch(error => {
                    this.errorList = [{ message: 'An error occurred while creating the user' }];
                    console.error(error);
                });

        }
    },
}
</script>