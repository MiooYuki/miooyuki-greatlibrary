<template>
  <div>
    <el-row justify="center">
      <el-col span="1">
        <h1 class="title">文档</h1>
      </el-col>
    </el-row>
    <el-row justify="center" gutter="30">
      <el-col v-for="doc in currentData" span="1">
        <el-card :body-style="{ padding: '0px', maxWidth: '256px' }" shadow="hover" style="border-radius: 14px;">
          <el-image :src="doc.img" />
          <div style="padding: 14px">
            <h4 class="card-title">{{ doc.title }}</h4>
            <div class="card-desc">{{ doc.desc }}</div>
            <a :href="doc.link"><el-button plain type="primary">阅读文档</el-button></a>
          </div>
        </el-card>
      </el-col>
    </el-row>
    <el-row justify="center" style="margin-top: 30px;">
      <el-col span="1">
        <el-pagination background layout="prev, pager, next"
                       :page-count="documentList.length" @current-change="switchPage" />
      </el-col>
    </el-row>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'

const documentList = ref([
  [
    {
      title: "Fabric wiki",
      desc: "Fabric 官方中文文档。",
      link: "/docs/fabric/install/setup.html",
      img: "/imgs/cover/fabric.png"
    },
    {
      title: "Apache Shiro",
      desc: "Shiro 官方文档翻译。",
      link: "/docs/shiro/menu.html",
      img: "/imgs/cover/shiro.png"
    },
    {
      title: "1.3",
      desc: "占位",
      link: "#",
      img: "/imgs/cover/default.png"
    },
    {
      title: "1.4",
      desc: "占位",
      link: "#",
      img: "/imgs/cover/default.png"
    },
  ],
  [
    {
      title: "2.1",
      desc: "占位",
      link: "#",
      img: "/imgs/cover/default.png"
    },
    {
      title: "2.2",
      desc: "占位",
      link: "#",
      img: "/imgs/cover/default.png"
    },
    {
      title: "2.3",
      desc: "占位",
      link: "#",
      img: "/imgs/cover/default.png"
    },
    {
      title: "2.4",
      desc: "占位",
      link: "#",
      img: "/imgs/cover/default.png"
    },
  ],
  [
    {
      title: "3.1",
      desc: "占位",
      link: "#",
      img: "/imgs/cover/default.png"
    },
    {
      title: "3.2",
      desc: "占位",
      link: "#",
      img: "/imgs/cover/default.png"
    },
    {
      title: "3.3",
      desc: "占位",
      link: "#",
      img: "/imgs/cover/default.png"
    },
    {
      title: "3.4",
      desc: "占位",
      link: "#",
      img: "/imgs/cover/default.png"
    },
  ]
])

const currentData = ref([])

const switchPage = (val: number) => {
  currentData.value = documentList.value[val - 1]
}

onMounted(() => {
  currentData.value = documentList.value[0]
})
</script>

<style lang="scss" scoped>
.title {
  padding: 0;
  margin: 0 0 50px;
  line-height: 64px;
  font-size: 64px;
  font-weight: bold;
  color: transparent;
  background: linear-gradient(to right, rgb(96,103,230), rgb(186,81,129));
  -webkit-background-clip: text;
}
.card-title {
  padding: 0;
  margin: 0 0 10px;
  font-weight: bold;
}
.card-desc {
  min-height: 80px;
  max-height: 80px;
  font-weight: lighter;
}
</style>