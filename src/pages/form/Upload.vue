<template>
    <div>
        <a-upload-dragger name="file" :multiple="true" action="//jsonplaceholder.typicode.com/posts/" @change="handleChange">
            <p class="ant-upload-drag-icon">
                <a-icon type="inbox" />
            </p>
            <p class="ant-upload-text">将文件拖到此处，或<em>点击上传</em></p>
            <p class="ant-upload-hint">文件大小不宜过大</p>
        </a-upload-dragger>
    </div>
</template>

<script>
import VueCoreImageUpload from 'vue-core-image-upload'
export default {
  name: 'Upload',
  data: function () {
    return {
      src: './static/img/img.jpg',
      fileList: []
    }
  },
  components: {
    VueCoreImageUpload
  },
  methods: {
    imageuploaded (res) {
      console.log(res)
    },
    handleError () {
      this.$notify.error({
        title: '上传失败',
        message: '图片上传接口上传失败，可更改为自己的服务器接口'
      })
    }
  }
}
</script>

<style scoped>
    .content-title{
        font-weight: 400;
        line-height: 50px;
        margin: 10px 0;
        font-size: 22px;
        color: #1f2f3d;
    }
    .pre-img{
        width:250px;
        height: 250px;
        margin-bottom: 20px;
    }
</style>
