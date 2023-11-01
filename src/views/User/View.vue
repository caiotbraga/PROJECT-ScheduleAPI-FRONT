<template>
    <div>
        <div class="card">
            <div class="card-header">
                <h4>
                    Users
                    <RouterLink to="/user/create" class="btn btn-primary float-end">
                        Add User
                    </RouterLink>
                </h4>
            </div>
            <div class="card-body">
                <table class="table table-bordered">
                    <thead>
                        <tr>
                            <th>Id</th>
                            <th>Name</th>
                            <th>Email</th>
                            <th>Number</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>

                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

    export default{
        name: 'users',
        data(){
            users: []
        },
        mounted(){
            this.getUsers();
            console.log('I am here')
        },
        methods: {
            getUsers(){
                axios.get('https://localhost:7156').then(res => {
                    console.log(res)
                });
            }
        },
    }
</script>