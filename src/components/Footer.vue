<template>
    <div>
        <ul id="footer-container">
            <li><a href="/" target="_self">Contact Us</a></li>
            <li></li>
            <li></li>
        </ul>

    </div>
</template>

<script>
export default {
    name: 'Footer',
    props: {
            subscription: String,
            logo: String
    },
}
</script>

<style>
#footer-container{
    display: flex;
    flex-direction: column;
    align-items: center;
    list-style: none;
    padding: 1rem;
}
</style>