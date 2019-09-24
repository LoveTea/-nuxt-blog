<template>
    <el-card class="comment">
        <div class="comment-header">
            <span class="name">{{comment.name}}</span>
            <small>
                <i class="el-icon-time"></i>
                {{new Date(comment.date).toLocaleString()}}
            </small>
        </div>
        <div class="comment-text">
            {{comment.text}}
        </div>
    </el-card>
</template>

<script>
export default {
    props: {
        comment: {
            type: Object,
            require: true
        }        
    }   
}
</script>

<style scoped>
    .comment {
        margin-bottom: 1rem;
    }

    .comment-header {
        display: flex;
        justify-content: space-between;
        margin-bottom: 0.5rem;
        font-size: 0.8rem;
    }

    .comment-text {
        white-space: pre-line;
    }

</style>
