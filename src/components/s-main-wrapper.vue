<template>
<div class="s-main-wrapper">
    <p>{{title}}</p>
    <sCatalogProfiles />
    <sIdProfile  /> -->
</div>
</template>

<script>
    import sCatalogProfiles from './s-catalog-profiles';
     import sIdProfile from './s-id-profile';

    
    export default{
        name: 's-main-wrapper',
        components: {
    sCatalogProfiles,
    sIdProfile,

},
        props: {},
        data() {
            return{
                title:"main wrapper"
            }
        },
        computed:{},
        methods:{},
        watch: {},
        mounted(){
            console.log('Hello i am alive!')
        }

    }
</script>

<style scoped>
    /* .s-main-wrapper {
        max-width: 900px;
        margin: 0 auto;
    } */
</style>