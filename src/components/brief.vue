<template>
  <div class="brief">
    <div class="avatar">
      <!-- contenteditable = "true" 让这个标签可以被编辑-->
<!--      <EditImage :src="require('@/assets/logo_name.png')" width="212" height="212" :isCircle="true" class="img"/>-->
      <div class="name" contenteditable="false">胡明轩</div>
      <div class="job" contenteditable="false">求职意向:java开发</div>
      <div class="location">
        <div class="location-name" contenteditable="false">现住地:重庆</div>
      </div>
    </div>
    <div class="info">
      <ul>
        <li>
          <span class="value" contenteditable="false">男</span>
          <br>
          <span class="key" contenteditable="false">性别</span>
        </li>
        <li>
          <span class="value" contenteditable="false">24</span>
          <br>
          <span class="key" contenteditable="false">年龄</span>
        </li>
        <li>
          <span class="value" contenteditable="false">本科</span>
          <br>
          <span class="key" contenteditable="false">学历</span>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
    import EditImage from '@/components/edit-image'

    export default {
        name: 'Brief',
        components: {
            EditImage
        }
    }
</script>
<style lang="less">
  .brief {
    width: 100%;
    height: 630px;
    background-color: #f6f7f7;

    .avatar {
      height: 500px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;

      & > .img {
        margin-bottom: 45px;
      }

      .name {
        font-size: 32px;
        margin-bottom: 14px;
      }

      .job {
        font-size: 24px;
        color: #555;
        margin-bottom: 16px;
      }

      .location {
        display: flex;
        align-itmes: center;

        .location-name {
          font-size: 20px;
          font-weight: bold;
          margin-left: 10px;
        }
      }
    }

    .info {
      height: 128px;
      width: 100%;
      overflow: hidden;
      border-top: 1px solid #dad8d7;
      border-bottom: 1px solid #dad8d7;

      & > ul {
        height: 100%;

        li:not(:last-child) {
          border-right: 1px solid #dad8d7;
        }

        li {
          float: left;
          width: 33.1%;
          height: 100%;
          overflow: hidden;
          text-align: center;
          padding-top: 25px;

          span {
            display: inline-block;
            margin: 0 auto;
          }

          .value {
            margin-bottom: 10px;
            font-size: 24px;
            font-weight: bold;
          }

          .key {
            font-size: 16px;
            font-weight: bold;
            color: #555;
          }
        }
      }
    }
  }

</style>
