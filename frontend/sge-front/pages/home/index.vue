<script setup lang="ts">
definePageMeta({
    middleware: 'auth'
})


const { signOut } = useAuth() 

const submitLogout = () => {
        signOut({redirect: false}).then(()=>{
            console.log('Successfully Logout!')
            navigateTo('/');

        }).catch((error)=>{
            console.log('Error when trying to logout: ', error);
        });
            
       
           
        
    }
</script>

<template>
    <div>
        <h1>Minha tela Home!</h1>
        <button type="submit" class="customButton" @click="submitLogout">SAIR</button>
    </div>
</template>