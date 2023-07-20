<template>
    <div>
        <!-- Messenger Chat plugin Code -->
        <div id="fb-root"></div>

        <!-- Your Chat plugin code -->
        <div id="fb-customer-chat" class="fb-customerchat"></div>
    </div>
</template>

<script>
export default {
    name: 'FacebookChatPlugin',
    mounted() {
        // Your Chat plugin code
        var chatbox = document.getElementById('fb-customer-chat');
        chatbox.setAttribute('page_id', '427891117590518');
        chatbox.setAttribute('attribution', 'biz_inbox');

        // Your SDK code
        window.fbAsyncInit = function () {
            FB.init({
                xfbml: true,
                version: 'v17.0',
            });
        };

        (function (d, s, id) {
            var js, fjs = d.getElementsByTagName(s)[0];
            if (d.getElementById(id)) return;
            js = d.createElement(s); js.id = id;
            js.src = 'https://connect.facebook.net/en_US/sdk/xfbml.customerchat.js';
            fjs.parentNode.insertBefore(js, fjs);
        }(document, 'script', 'facebook-jssdk'));
    },
};
</script>
