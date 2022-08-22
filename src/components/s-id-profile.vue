<template>

<div class="s-id-profile"> </div>

    <img class="s-id-profile-image" :src=" require('../assets/images' + profile_data.image) " alt="img">
    <p class="s-id-profile-name">{{profile_data.name}}</p>
    <button class="s-id-profile-personal-page" pagebtn>go to personal page</button>
    <button class="s-id-profile-personal-albums" contentbtn>go to personal album</button>
    <button class="s-id-profile-personal-posts" contentbtn>go to personal posts</button>
    <SIdProfileAlbums></SIdProfileAlbums>
    <SIdProfilePosts></SIdProfilePosts>
</template>

<script>
import SIdProfileAlbums from './s-id-profile-albums.vue';
import SIdProfilePosts from './s-id-profile-posts.vue';
    export default{
    name: "s-id-profile",
    props: {
        profile_data:{
            type: Object,
            default() {
                return{}
            }
        }
    },
    data() {
        return {};
    },
    computed: {},
    components: { SIdProfileAlbums, SIdProfilePosts }
}
</script>

<style>
    /* .s-id-profile{
        flex-basis: 25%;
        box-shadow: 0 0 8px 0 #d1cece;
    } */

</style>