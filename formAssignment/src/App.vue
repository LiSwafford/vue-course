<template>
    <div class="container">
        <form v-if="!isSubmitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->
                <FullName v-model="userInfo.fullName"></FullName>
                    <div class="form-group">
                        <label for="email">Mail</label>
                        <input
                            type="text"
                            id="email"
                            class="form-control"
                            v-model="userInfo.email"
                            >
                            <!-- <p>{{ userInfo.email }}</p> -->
                    </div>
                    <div class="form-group">
                        <label for="password">Password</label>
                        <input 
                        type="password"
                        id="password"
                        class="form-control"
                        v-model.lazy="userInfo.password">
                        <!-- <p>{{userInfo.password}}</p> -->
                    </div>
                    <div class="form-group">
                        <label for="storeData">Store Data?</label>
                        <label for="yes">
                            <input
                                type="radio"
                                value="Yes"
                                v-model="storeData"> Yes
                        </label>
                        <label for="no">
                            <input
                                type="radio"
                                value="No"
                                v-model="storeData"> No
                        </label>
                    </div>

                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <button
                        class="btn btn-primary"
                        @click.prevent="submitted"
                        >Submit
                    </button>
                </div>
            </div>
        </form>
        <hr>
        <div class="row"
        v-if="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ userInfo.fullName }}</p>
                        <p>Mail: {{ userInfo.email}}</p>
                        <p>Password: {{ userInfo.password }}</p>
                        <p>Store in Database?: {{ storeData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import FullName from "./FullName.vue";
    export default {
        data() {
            return {
                userInfo:{
                    fullName : "LI Swafford",
                    email : "",
                    password : ""
                },
                isSubmitted: false,
                storeData: "Yes"
            }
        },
        methods: {
            submitted(){
                this.isSubmitted = true;
            }
        },
        components: {
            FullName
        }
    }
</script>

<style>
</style>
