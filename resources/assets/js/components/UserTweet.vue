<template>
    <div>
        <div class="all-tweet" v-for="(tweet, index) in tweets">
            <div class="t-show-wrap">
                <div class="t-show-inner">
                    <!-- this div is for retweet icon
                        <div class="t-show-banner">
                            <div class="t-show-banner-inner">
                                <span><i class="fa fa-retweet" aria-hidden="true"></i></span><span>Screen-Name Retweeted</span>
                            </div>
                        </div>
                    -->
                    <div class="t-show-popup">
                        <div class="t-show-head">
                            <div class="t-show-img">
                                <img :src="getPic(user.profile_image)"/>
                            </div>
                            <div class="t-s-head-content">
                                <div class="t-h-c-name">
                                    <span>
                                        <!--PROFILE-LINK-->
                                        <a href="#">{{ user.screen_name }}</a>
                                    </span>
                                    <span>@{{ user.username }}</span>
                                    <span>{{ tweet.created_at }}</span>
                                </div>
                                <div class="t-h-c-dis">
                                    {{ tweet.tweet }}
                                </div>
                            </div>
                        </div>
                        <!--tweet show head end-->

                        <div class="t-show-body" v-if="tweet.image">
                            <div class="t-s-b-inner">
                                <div class="t-s-b-inner-in">
                                    <!--TWEET-IMAGE-->
                                    <img src="" class="imagePopup"/>
                                </div>
                            </div>
                        </div>
                        <!--tweet show body end-->
                    </div>
                    <div class="t-show-footer">
                        <!--like vue-->
                        <!--<like :id="tweet.id" :tweet_id="tweet.id" :show-modal="showPopup"></like>-->
                    </div>
                </div>
            </div>
            <!--<retweet v-if="showModal" :tweet="tweet"></retweet>-->
        </div>
    </div>
</template>

<script>
    export default {
        props: ['tweets', 'user'],
        mounted() {

        },
        methods: {
            getPic(src) {
                return '../../'+ src;
            }
        }
    }
</script>