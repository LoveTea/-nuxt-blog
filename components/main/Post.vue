<template>
 <el-card
    shadow="hover"
    :body-style="{padding: 0}"
    class="post"
 >
    <header slot="header" class="post-header">
        <h3>{{post.title}}</h3>
        <small>
            <i class="el-icon-time"></i>
            {{new Date(post.date).toLocaleString()}}
            </small>
    </header>
    <div class="post-body">
        <img
         :src="post.imageUrl"
         alt="post-img"
         class="post-image">
    </div>
    <footer class="post-footer">
        <el-button round @click="openPost">Открыть</el-button>

        <span>
            <i class="el-icon-message">{{post.comments.length}}</i>
        </span>
    </footer>
 </el-card>
</template>

<script>
export default {
    props: {
        post: {
            type: Object,
            required: true
        }
    },
    methods: {
        openPost() {
            const id = this.post._id
            this.$router.push(`/post/${id}`)
        }
    }
    
}
</script>

<style scoped>
    .post {
        margin-bottom: 1.5em;
    }

    .post-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .post-img {
        width: 100%;
        height: auto;

    }
    .post-footer {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem;
    }

</style>
