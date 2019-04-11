<template>
    <div class="container">
        <form v-if="!submitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <app-full-name
                    v-model="fullName"
                    >

                    </app-full-name>
                    <div class="form-group">
                        <label for="email">Mail</label>
                        <input
                            type="text"
                            id="email"
                            class="form-control"
                            v-model="userInfo.mail"
                        >        
                    </div>
                    <div class="form-group">
                        <label for="password">Password</label>
                        <input
                            type="password"
                            id="password"
                            class="form-control"
                            v-model="userInfo.password"
                        >        
                    </div>
                    <div class="form-group">
                        Save in Database? 
                        <label for="yes">
                            <input
                                type="radio"
                                id="yes"
                                value="yes"
                                v-model="submitDB"
                                > Yes
                        </label>
                        <label for="no">
                            <input
                                type="radio"
                                id="no"
                                value="no"
                                v-model="submitDB"
                                > No
                        </label>
                </div>
                    
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->

                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
                
            </div>
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                <button
                type="submit"
                class="btn btn-primary"
                @click.prevent="submit"
                > Submit Form </button>
                </div>
        </form>
        <hr>
        <div v-if="submitted" class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{fullName}}</p>
                        <p>Mail: {{userInfo.mail}} </p>
                        <p>Password: {{userInfo.password}} </p>
                        <p>Store in Database?:  {{submitDB}} </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import FullName from './FullName.vue'

    export default {
        data(){
            return {
                fullName: 'Carlos Rodriguez',
                userInfo : {
                    
                    mail: 'Type in Email',
                    password: 'Type in Password'
                },
                submitDB: 'no',
                submitted: false
            }
        },
        methods: {
            submit(){
                this.submitted = true;
            }
        },
        components: {
            appFullName: FullName
        }
    }
</script>

<style>
</style>
