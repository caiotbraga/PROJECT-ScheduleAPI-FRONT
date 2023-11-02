<template>
    <div class="container">
        <div class="card" id="user-table">
            <div class="card-header">
                <h4>
                    Users
                    <RouterLink to="/users/create" class="btn btn-primary float-end">
                        Add User
                    </RouterLink>
                </h4>
            </div>
            <div class="card-body">
                <table class="table table-bordered">
                    <thead>
                        <tr class="text-center">
                            <th >Id</th>
                            <th>Name</th>
                            <th>Email</th>
                            <th>Number</th>
                            <th>Actions</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(users, index) in this.users" :key="index" class="text-center">
                            <td>{{ users.id }}</td>
                            <td>{{ users.userName }}</td>
                            <td>{{ users.email }}</td>
                            <td>{{ users.phoneNumber }}</td>
                            <td class="buttons-c" id="align-buttons">
                                <RouterLink :to="{ path: '/users/edit/'+users.id }" class="btn btn-primary text-center align-middle">
                                    Edit
                                </RouterLink>
                                <button type="button" @click="deleteUser(users.id)"  class="btn btn-danger text-center align-middle">
                                    Delete
                                </button>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    name: 'users',
    data() {
        return{
            users: []
        } 
    },
    mounted() {
        this.getUsers();
    },
    methods: {
        getUsers() {
            axios.get('http://localhost:7156/user').then(res => {
                this.users = res.data;
                console.log(this.users);
            });
        },
        deleteUser(userId){
        if(confirm('Are you sure that you want to delete this user?')){
            axios.delete(`http://localhost:7156/user/${userId}`)
            .then(res => {
                alert("User sucessfully deleted!")
                this.getUsers();
                this.$router.replace('/users');
            })
            .catch(error => {
                    this.errorList = [{ message: 'An error occurred while creating the user' }];
                    console.error(error);
                });;
        }
    }
    },
}
</script>