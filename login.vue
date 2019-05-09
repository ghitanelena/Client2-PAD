<template>
    <div id="login">
        <h1>Admin</h1>
        <input type="text" name="username" v-model="input.username" placeholder="Username" />
        <input type="password" name="password" v-model="input.password" placeholder="Password" />
        <br>
        <div id="button">
        <button  v-on:click="post">Create account</button> 
        <button  v-on:click="post" >Delete account</button>
        </div>
       
    </div>
</template>

<script>
    export default {
        name: 'Login',
        data() {
            return {
                input: {
                    username: "",
                    password: ""
                }
            }
        },
        methods: {
            post: function(){
            this.$http.post('https://jsonplaceholder.typicode.com/posts',{
                title:this.input.username,
                body:this.input.password,
                userId:1
            }).then(function(data){
                console.log(data);
            })
        }
        }
        
    }
</script>

<style scoped>
    #login {
        width: 500px;
        border: 1px solid #CCCCCC;
        background-color: #FFFFFF;
        margin: auto;
        margin-top: 200px;
        padding: 20px;
    }
    #button {
        display:inline-block;
        font-size: 16px;
        justify-content: space-between;
        margin-right:150px;
         
         border:none;
         color:darkslategrey;
        padding: 15px 32px;
        text-align: center;
    }

</style>