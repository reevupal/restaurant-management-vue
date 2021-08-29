<template>
    <Header />
    <h3>Welcome User, Home page is there</h3>
</template>
<script>
import Header from './Header.vue';

export default {
    name:'Home',
    components:{
        Header
    },
    mounted(){
        let userDetails= localStorage.getItem('user-info');

        if(!userDetails){
            this.$router.push({ name: 'SignUp' });
        }
    }
}
</script>