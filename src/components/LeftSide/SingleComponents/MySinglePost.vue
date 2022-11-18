<template>
    <div class="post">
        <!-- Loading Component -->
        <div class="postLoadingHeader" v-if="loading == true">
            <div class="profileLoading"></div>
            <div class="profileNameLoading"></div>
        </div>
        <!-- Render Component -->
        <div class="postHeader" v-else>
            <img class="profileImg" :src="post.profile_picture" alt="Profile Img">
            <div class="postName">
                <h4>{{ post.profile_name }}</h4>
                <h5>{{ post.profile_fullname }}</h5>
            </div>
        </div>
        <!-- Loading Component -->
        <div class="postLoadingContent" v-if="loading == true"></div>
        <div v-else>
            <div class="borderComments">
                <!-- Render Component --> 
                <div class="postContent">
                    <img class="postImg" :src="post.post_image" alt="Post Img">
                    <div class="postIcon">
                        <i class="fa-regular fa-heart"></i>
                        <i class="fa-regular fa-comment"></i>
                        <i class="fa-regular fa-share-from-square"></i>
                    </div>
                    <div class="postLikes">
                        <strong v-if="post.likes.length == 1">Piace a {{ post.likes[0].username}}</strong>
                        <strong v-if="post.likes.length == 2">Piace a {{ post.likes[0].username}} e {{ post.likes[1].username}}</strong>
                        <strong v-if="post.likes.length >= 3">Piace a {{ post.likes[0].username}}, {{ post.likes[1].username}} e altre {{ post.likes.length - 2}} persone</strong>
                    </div>
                    <div class="postText">
                        <strong>{{ post.profile_name }}</strong>
                        <span>{{ post.post_text }}</span>
                    </div>
                </div>
                <!-- Loading Component -->
                <div class="postLoadingComments" v-if="loading == true"></div>
                <!-- Render Component -->
                <div class="postComments" v-else>
                    <div class="postCommentsNumber">
                        <span v-if="post.comments.length == 0">Nessun commento</span>
                        <span v-else-if="post.comments.length == 1">1 commento totale</span>
                        <span v-else-if="post.comments.length >= 2">{{ post.comments.length }} commenti totali</span>
                        <div v-if="post.comments.length >= 4">
                            <a @click="showComments = !showComments" class="myLink" href="#">Mostra tutti</a>
                        </div>
                    </div>
                    <div v-if="post.comments.length > 0 && post.comments.length <= 3">
                        <div class="singleComment" v-for="(comment, index) in post.comments" :key="index">
                            <strong>{{ comment.username }}</strong>
                            <span class="commentText">{{ comment.text }}</span>
                        </div>
                    </div>
                    <div v-else-if="post.comments.length >= 3  && showComments == false">
                        <div class="singleComment" v-for="(comment, index) in post.comments.slice(0,3)" :key="index">
                            <strong>{{ comment.username }}</strong>
                            <span class="commentText">{{ comment.text }}</span>
                        </div>
                    </div>
                    <div v-else-if="post.comments.length >= 3 && showComments == true">
                        <div class="singleComment" v-for="(comment, index) in post.comments" :key="index">
                            <strong>{{ comment.username }}</strong>
                            <span class="commentText">{{ comment.text }}</span>
                        </div>
                    </div>
                </div>
                <div class="writeComment">
                    <img src="../../../assets/images/profile.jpg" alt="Profile Pic" class="profileImgSmall">
                    <input type="text" name="newComments">
                </div>
            </div>
        </div>
    </div>
</template>
  
<script>
    export default {
        name: 'MySinglePost',
        data() {
            return {
                numberLikes: 0,
                showComments: false,
                newComments: ''
            }
        },
        props: {
            post: Object,
            loading: Boolean
        },
    }
</script>

<style scoped lang="scss">
 @import '../../../assets/styles/mixin.scss';
 @import '../../../assets/styles/vars.scss';
    .post {
        margin: 25px 10px;
        padding: 10px;
        .postHeader {
            @include verticalAlign;
            padding: 5px;
            border: 1px  solid lightgray;
            border-radius: 15px 15px 0 0;
            .postName {
                padding-left: 10px;
            }
        }
        .postContent {
            .postImg {
                width: 450px;
            }
            .postText {
                padding-left: 10px;
                strong {
                    padding-right: 7px;
                }
            }
            .postLikes {
                margin: 5px 0;
                padding-left: 10px;
            }
            .postIcon {
                padding-left: 10px;
                margin: 5px 0;
                i {
                    font-size: 22px;
                    color: $boolgram-primary;
                    margin-right: 25px;
                    cursor: pointer;
                }
            }
        }
        .postComments {
            padding-left: 10px;
        }
        .postCommentsNumber {
            margin: 5px 0;
            display: flex;
            justify-content: space-between;
            span {
                color: gray
            }
        }
        .postLoadingHeader {
            @include verticalAlign;
        }
        .profileNameLoading {
            width: 150px;
            height: 30px;
            display: inline-block;
            margin-left: 10px;
        }
        .postLoadingContent {
            width: 450px;
            height: 450px;
            background-color: lightgray;
            margin: 10px 0;
        }
        .postLoadingComments{
            background-color: lightgray;
            height: 100px;
            width: 100%;
        }
        .singleComment {
            margin: 5px 0;
        }
        .commentText {
            margin-left: 5px;
        }
        .borderComments {
            padding-bottom: 15px;
            border: 1px  solid lightgray;
            border-radius: 0 0 15px 15px;
        }
        .writeComment {
            margin-top: 10px;
            padding-left: 10px;
            @include verticalAlign;
            img {
                margin-right: 5px;
            }
            input {
                width: 90%;
                padding: 3px 8px;
                border-radius: 15px;
                border: 1px solid $boolgram-primary;
            }
        }
    }    
</style>