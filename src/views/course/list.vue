<template>
  <div class="">
    <section>
      <nav id="cloudclassroom" class>
        <div class="title_list">
          <tag :classIfy="classIfy" :filterList="filterList"></tag>
        </div>
        <section id="cl_card">
          <card :newList="newList" :bpyStyle="bpyStyle"></card>
        </section>
      </nav>
    </section>
    <Footer class="w-200"></Footer>
  </div>
</template>

<script>
import Card from "@/components/Card";
import Tag from "@/components/Tag.vue";
import Footer from "@/components/Footer.vue";
export default {
  // props: {
  //   bpyStyle: Function,
  // },
  components: { Card, Tag, Footer },
  computed: {
    newList() {
      const { hotcourseList, filtrate } = this;
      var reg = new RegExp(filtrate, "ig");
      if (filtrate !== "全部") {
        return hotcourseList.filter((item) => item.tag.match(reg) !== null);
      } else {
        return hotcourseList;
      }
    },
  },
  methods: {
    filterList(value) {
      this.filtrate = value;
    },
    bpyStyle(index) {
      return (index *= -200);
    },
  },
  data() {
    return {
      filtrate: "全部",
      classIfy: [
        "全部",
        "云计算",
        "软件开发",
        "大数据",
        "架构设计",
        "物联网",
        "鲲鹏",
      ],
      hotcourseList: [
        {
          url:
            "https://education.huaweicloud.com/programs/16cfbeb8-40dd-48b3-a490-e884f8bd2814/about?isAuth=0&cfrom=hwc",
          title: "物联网开发者系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "物联网 ",
        },
        {
          url:
            "https://education.huaweicloud.com/programs/fcdaaec3-bd7a-41a1-8532-f3a9a5bd22ff/about?isAuth=0&cfrom=hwc",
          title: "鲲鹏开发者系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "鲲鹏",
        },
        {
          url:
            "https://education.huaweicloud.com/programs/d1e194ae-1ea6-4390-8cc6-b57fd85e4f4c/about",
          title: "开发者系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "软件开发",
        },
        {
          url:
            "https://education.huaweicloud.com/programs/cbfcfb5a-327a-45ed-a2be-c81856ea98a3/about",
          title: "EI智能数据湖系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "大数据",
        },
        {
          url:
            "https://education.huaweicloud.com/programs/b32c57cb-3b77-413e-a4be-7baca88cdeab/about",
          title: "云计算初学者系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "云计算",
        },
        {
          url:
            "https://education.huaweicloud.com/programs/ea15590b-277a-4358-bd64-e27131dfb378/about",
          title: "架构师系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "架构设计",
        },
        {
          url:
            "https://education.huaweicloud.com/programs/16cfbeb8-40dd-48b3-a490-e884f8bd2814/about?isAuth=0&cfrom=hwc",
          title: "物联网开发者系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "物联网 ",
        },
        {
          url:
            "https://education.huaweicloud.com/programs/fcdaaec3-bd7a-41a1-8532-f3a9a5bd22ff/about?isAuth=0&cfrom=hwc",
          title: "鲲鹏开发者系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "鲲鹏",
        },
        {
          url:
            "https://education.huaweicloud.com/programs/d1e194ae-1ea6-4390-8cc6-b57fd85e4f4c/about",
          title: "开发者系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "软件开发",
        },
        {
          url:
            "https://education.huaweicloud.com/programs/cbfcfb5a-327a-45ed-a2be-c81856ea98a3/about",
          title: "EI智能数据湖系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "大数据",
        },
        {
          url:
            "https://education.huaweicloud.com/programs/b32c57cb-3b77-413e-a4be-7baca88cdeab/about",
          title: "云计算初学者系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "云计算",
        },
        {
          url:
            "https://education.huaweicloud.com/programs/ea15590b-277a-4358-bd64-e27131dfb378/about",
          title: "架构师系列课程",
          user: "Classroom",
          school: "华为云",
          tag: "架构设计",
        },
      ],
    };
  },
};
</script>


<style >
@import url("../../style/cl_card");
.card_bg {
  width: 100%;
  height: 200px;
  /* width: 280px; */
  background-image: url(https://res.devcloud.huaweicloud.com/obsdevui/diploma/8.1.24.002/index-base.8219f4736a92c4a4f526.png);
  border-radius: 12px 12px 0 0;
  box-sizing: border-box;
}
</style>