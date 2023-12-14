<template>
  <div class="map_container">
    <vue-draggable-resizable
      class="vue_draggable_resizable"
      w="auto"
      h="auto"
      :x="x"
      :y="y"
      :handles="[]"
      @dragging="onDrag"
      @resizing="onResize"
    >
      <div class="map_content_box">
        <div
          class="map_content"
          v-for="item in okrTreeData"
          :key="item.id"
          @click="handleDomClick"
        >
          <vue-okr-tree
            ref="okrTree"
            :data="item.data.right"
            direction="horizontal"
            show-collapsable
            node-key="id"
            showNodeNum
            :render-content="renderContent"
            :node-btn-content="nodeBtnContent"
            @node-click="handleNodeClick"
            @node-expand="handleNodeExpand"
            @node-collapse="handleNodeCollapse"
          />
        </div>
      </div>
    </vue-draggable-resizable>
  </div>
</template>

<script>
import { VueOkrTree } from "vue-okr-tree";
import "vue-okr-tree/dist/vue-okr-tree.css";
import VueDraggableResizable from "vue-draggable-resizable";
import "vue-draggable-resizable/dist/VueDraggableResizable.css";

export default {
  name: "MyOkrTree",
  props: {
    okrTreeData: {
      type: Array,
    },
  },
  components: {
    VueOkrTree,
    VueDraggableResizable,
  },
  data() {
    return {
      width: 0,
      height: 0,
      x: 0,
      y: 0,
      testData: [],
      img: "",
      positionFlag: false,
      customColors: [
        { color: "#D8423E", percentage: 50 },
        { color: "#EEAF00", percentage: 80 },
        { color: "#3DB373", percentage: 100 },
        { color: "#3F9EFF", percentage: 101 },
      ],
      childrenNum: 0,
      parentNum: 0,
      sex: sessionStorage.getItem("sex"),
      user: {},
      propStyle: {
        fontSize: "12px",
        width: "24px",
        height: "24px",
      },
      propScale: "0.7",
      ossUrl: '',
    };
  },
  mounted() {
    this.ossUrl = this.$config.ossUrl
    this.user = this.$store.state.user
  },
  methods: {
    handleDomClick() {

      let card_wrap = document.getElementsByClassName("card_wrap");
      let card_wrap_arr = Array.from(card_wrap);
      card_wrap_arr.forEach((element) => {
        if (
          element.className.indexOf("current_select") !== -1 &&
          element.className.indexOf("current_empty_left_border") !== -1
        ) {
          // element.classList.remove("current_select");
          // element.classList.remove("current_empty_left_border");
        }
      });
    },
    onResize: function (x, y, width, height) {
      this.x = x;
      this.y = y;
      this.width = width;
      this.height = height;
    },
    onDrag: function (x, y) {
      this.x = x;
      this.y = y;
    },
    handleNodeClick(data, node, self) {
      this.$emit("showDetailDrawer");
    },
    handleNodeExpand(data, node, self) {},
    handleNodeCollapse(data, node, self) {},
    nodeBtnContent(h, node) {
      console.log(node, "node");
      return (
        <div class="org-chart-node-btn-text">{node.childNodes.length || 0}</div>
      );
    },
    renderContent(h, node) {
      const cls = ["card_wrap"];
      if (node.data.deptType === '0') {
        cls.push("company");
      }
      if (node.data.deptType === "1") {
        cls.push("center");
      }
      if (node.data.deptType === "2") {
        cls.push("platform");
      }
      if (node.data.deptType === "3") {
        cls.push("dept");
      }
      if (node.data.deptType === "4") {
        cls.push("self");
      }
      if (node.isCurrent) {
        cls.push("current_select current_empty_left_border");
      }
      return (
        <div class={cls}>
          {
            <div class="card_content">
              <div class="card_content_left">
                {this.user.avatar ? (<div style="display: flex;">
                  <el-avatar size={20}
                             src="https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png"></el-avatar>
                </div>) : (<div style="display: flex;">
                  <el-avatar size={20}>{this.user.name}</el-avatar>
                </div>)}
              </div>
              <div class="card_content_right">
                <div class="card_content_right_top">
                  <span>{this.user.name}</span>
                  <span>50%</span>
                </div>
                <div class="card_content_right_top" style="margin-top: 5px">
                  <span>研发中心</span>
                  <span>{node.data.budget}万元</span>
                </div>
                <div class="card_content_right_bottom">
                  <span>{node.data.planName}</span>
                </div>
              </div>
            </div>
          }
        </div>
      );
    },
  },
};
</script>

<style lang="scss">
@import "./index.scss";
</style>
