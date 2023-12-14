<template>
  <el-drawer
    size="680px"
    :visible.sync="dialogVisible"
    :direction="direction"
    :show-close="false"
    @close="close"
  >
    <div slot="title" class="demo-drawer__header">
      <div class="drawer_header_wrap">
        <div class="drawer_header_wrap_left">
          <div class="user_box">
            <p>uuu</p>
            <span>技术部</span>
          </div>
        </div>
        <div class="drawer_header_wrap_right">
          <span>查看详情</span>
          <i class="el-icon-close" @click="close"></i>
        </div>
      </div>
    </div>
    <div class="demo-drawer__content">
      <div class="drawer_content_wrap">
        <div class="drawer_content_wrap_container">
          <div class="ObjectiveItem_objective_content">
            <div class="ObjectiveItem_objective_icon"></div>
            <div class="ObjectiveItem_objective_content_center">
              <div class="ObjectiveItem_objective_content_center_top">
<!--                <img src="@/assets/img/up.svg" alt="" class="up_svg" />-->
                <div class="ObjectiveItem_objective_content_center_top_user">
                  <span>www</span>，<span>eee</span>
                </div>
              </div>
              <div class="ObjectiveItem_objective_content_center_bottom">
                说我容光焕发杜尔股份很烦IE我回味回味很烦IE我划分为今日佛业务回家喔i氛围h9firwe回复惹我回家哦废物回家佛IE我就否无额很烦IE我fjo9iwe会发改委就分为法布尔司法发版后IE我很烦IE我
              </div>
            </div>
            <div class="ObjectiveItem_objective_content_right">
              <div class="ObjectiveItem_objective_content_right_progress">
                <div class="progress_top">进度</div>
                <div class="progress_center">
                  <el-progress
                    class="progress"
                    type="circle"
                    :percentage="getPercentage()"
                    :show-text="false"
                    :width="18"
                    :height="18"
                    :color="getProgressColor()"
                    :stroke-width="4"
                  ></el-progress>
                  <span>25%</span>
                </div>
              </div>
              <div class="ObjectiveItem_objective_content_right_weight">
                <div class="weight_top">权重</div>
                <div class="weight_center">100%</div>
              </div>
              <div class="ObjectiveItem_objective_content_right_score">
                <div class="score_top">总分</div>
                <div class="score_center">0.2</div>
              </div>
            </div>
          </div>
          <div class="ObjectiveItem_objective_bottom">
<!--            <img src="@/assets/img/down.svg" alt="" class="down_svg" />-->
            <div class="ObjectiveItem_objective_bottom_content">
              <span>rrr</span>
            </div>
          </div>
        </div>
        <ul class="kr_list_wrap">
          <li>
            <div class="kr_result_content">
              <div class="kr_result_content_center">
                <p>kkkkkkkkkkkkkkkk​<span>@yyy</span><span>@iii</span></p>
              </div>
              <div class="kr_result_content_right">
                <div class="right_progress">
                  <div class="progress_center">
                    <el-progress
                      class="progress"
                      type="circle"
                      :percentage="getPercentage()"
                      :show-text="false"
                      :width="18"
                      :height="18"
                      :color="getProgressColor()"
                      :stroke-width="4"
                    ></el-progress>
                    <span>25%</span>
                  </div>
                </div>
                <div class="right_weight">
                  <div class="weight_center">100%</div>
                </div>
                <div class="right_score">
                  <div class="score_center">0.2</div>
                </div>
              </div>
            </div>
          </li>
          <li>
            <div class="kr_result_content">
              <div class="kr_result_content_center">
                <p>kkkkkkkkkkkkkkkk​<span>@ll</span><span>@ddd</span></p>
              </div>
              <div class="kr_result_content_right">
                <div class="right_progress">
                  <div class="progress_center">
                    <el-progress
                      class="progress"
                      type="circle"
                      :percentage="getPercentage()"
                      :show-text="false"
                      :width="18"
                      :height="18"
                      :color="getProgressColor()"
                      :stroke-width="4"
                    ></el-progress>
                    <span>25%</span>
                  </div>
                </div>
                <div class="right_weight">
                  <div class="weight_center">100%</div>
                </div>
                <div class="right_score">
                  <div class="score_center">0.2</div>
                </div>
              </div>
            </div>
          </li>
        </ul>
        <div class="drawer_content_wrap_progress">
          <div class="drawer_content_wrap_progress_left">
            <i class="el-icon-document"></i>
          </div>
          <div class="drawer_content_wrap_progress_center">
            <p>进度记录</p>
            <div>
              公共加入分为托管人考托管费热帖奇偶太过分我看见推广吗太浓酷热派克特科技破给她的听过课配开通怕热跨平台各欧特瑞不辜负日本国你让他废物你妇科你付款较为内容范围热热热呃呃呃呃呃呃呃呃呃
            </div>
          </div>
        </div>
      </div>
    </div>
  </el-drawer>
</template>

<script>
export default {
  name: "OkrTreeDetail",
  components: {
  },
  props: {
    title: String,
    periodTypeSelect: Array,
    data: Object,
    visible: {
      type: Boolean,
      default: false,
    },
  },
  watch: {
    visible(newVal) {
      this.dialogVisible = newVal;
    },
  },
  data() {
    return {
      dialogVisible: this.visible,
      loading: false,
      direction: "rtl",
      sex: sessionStorage.getItem("sex"),
      nickname: '利峰',
    };
  },
  created() {},
  mounted() {},
  methods: {
    close() {
      this.$emit("closeDetailDrawer");
    },
    // 获取百分比
    getPercentage(okr) {
      // if (!okr.progress) {
      //   return 0;
      // } else {
      //   if (okr.progress >= 1) {
      //     return 100;
      //   } else {
      //     return +(okr.progress * 100).toFixed(0);
      //   }
      // }
    },
    // 获取状态颜色
    getProgressColor(okr, type) {
      // if (type === "objective") {
      //   if (okr.remark === "1") {
      //     //  取目标状态
      //     if (okr.status === "0") {
      //       return "#5272E5";
      //     } else if (okr.status === "1") {
      //       return "#E79144";
      //     } else if (okr.status === "2") {
      //       return "#D2655D";
      //     } else {
      //       return "#5272E5";
      //     }
      //   } else {
      //     //  默认
      //     const isHaveTwo = okr.okrProcessList.some((a) => a.status === "2");
      //     const isHaveOne = okr.okrProcessList.some((b) => b.status === "1");
      //     if (isHaveOne) {
      //       if (isHaveTwo) {
      //         return "#D2655D";
      //       } else {
      //         return "#E79144";
      //       }
      //     } else {
      //       if (isHaveTwo) {
      //         return "#D2655D";
      //       } else {
      //         return "#5272E5";
      //       }
      //     }
      //   }
      // } else if (type === "kr") {
      //   if (okr.status === "0") {
      //     return "#5272E5";
      //   } else if (okr.status === "1") {
      //     return "#E79144";
      //   } else if (okr.status === "2") {
      //     return "#D2655D";
      //   }
      // }
    },
  },
};
</script>

<style scoped lang="scss">
.demo-drawer__header {
  .drawer_header_wrap {
    padding: 16px 24px;
    border-bottom: 1px solid #dee0e3;
    display: -ms-flexbox;
    display: flex;
    -ms-flex-align: center;
    align-items: center;
    justify-content: space-between;

    .drawer_header_wrap_left {
      display: flex;

      .user_box {
        margin-left: 12px;
        p {
          font-size: 16px;
          // font-weight: 500;
          // line-height: 24px;
          color: #1f2329;
          overflow: hidden;
          text-overflow: ellipsis;
          white-space: nowrap;
        }
        span {
          font-size: 14px;
          color: #8f959e;
          overflow: hidden;
          text-overflow: ellipsis;
          white-space: nowrap;
        }
      }
    }

    .drawer_header_wrap_right {
      display: flex;
      align-items: center;
      span {
        font-size: 16px;
        color: #3370ff;
        line-height: 24px;
        margin-right: 24px;
        cursor: pointer;
      }

      .el-icon-close {
        font-size: 20px;
        color: #909399;
        cursor: pointer;
      }

      .el-icon-close:hover {
        color: #4273f6;
      }
    }
  }
}
::v-deep.el-drawer__header {
  padding: 0px;
  margin-bottom: 0px;
}
::v-deep .el-drawer:focus {
  outline: 0;
}
.demo-drawer__content {
  padding: 24px 24px 0;
  overflow-y: auto;
  position: relative;
  height: calc(100vh - 79px);

  .drawer_content_wrap {
    border: 1px solid #e4e5e7;
    margin-bottom: 20px;
    box-shadow: none;
    border-radius: 4px;
    padding-top: 12px;
  }
  .drawer_content_wrap_container {
    position: relative;
    border-bottom: 1px solid transparent;
    padding: 0 23px 12px 59px;
    .ObjectiveItem_objective_content {
      -ms-flex: 1;
      flex: 1;
      display: -ms-flexbox;
      display: flex;
      position: relative;

      .ObjectiveItem_objective_icon {
        position: absolute;
        left: -44px;
        top: 18px;
        width: 32px;
        height: 32px;
        margin-right: 12px;
        border-radius: 50%;
        background: url(data:image/png;base64,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);
        background-size: cover;
        z-index: 2;
      }

      .ObjectiveItem_objective_content_center {
        flex: 1;
        .ObjectiveItem_objective_content_center_top {
          position: relative;
          color: #8f959e;
          font-size: 12px;

          .up_svg {
            position: absolute;
            width: 24px;
            height: 24px;
            left: -28px;
            top: 9px;
          }

          .ObjectiveItem_objective_content_center_top_user {
            margin-right: 16px;
            white-space: pre-wrap;
            display: -ms-flexbox;
            display: flex;
            -ms-flex-flow: row wrap;
            flex-flow: row wrap;
            span {
              cursor: pointer;
              &:hover {
                color: #3370ff !important;
              }
            }
          }
        }
        .ObjectiveItem_objective_content_center_bottom {
          -ms-flex: 1;
          flex: 1;
          padding-top: 4px;
          padding-bottom: 4px;
          margin-right: 36px;
          color: #1f2329;
          font-size: 16px;
          line-height: 24px;
          margin-right: 23px;
          font-weight: 400;
          transition: min-height 0.35s ease-out;
          overflow-y: auto;
          color: #1f2329;
          word-break: break-word;
          -webkit-transform: none;
          transform: none;
          -webkit-user-select: none;
          -moz-user-select: none;
          -ms-user-select: none;
          user-select: none;
        }
      }

      .ObjectiveItem_objective_content_right {
        display: -ms-flexbox;
        display: flex;
        min-height: 32px;

        .ObjectiveItem_objective_content_right_progress {
          width: 77px;
          text-align: right;
          display: inline-block;
          line-height: 22px;
          color: #646a73;
          padding-top: 1px;

          .progress_top {
            line-height: 18px;
            font-size: 12px;
            color: #8f959e;
          }

          .progress_center {
            margin-top: 5px;
            color: #646a73;
            white-space: nowrap;
            display: flex;
            align-items: center;
            justify-content: flex-end;
            .progress {
            }
            span {
              display: inline-block;
              width: 43px;
            }
          }
        }

        .ObjectiveItem_objective_content_right_weight {
          margin-left: 16px;
          width: 56px;
          text-align: right;
          padding: 0 8px;
          .weight_top {
            line-height: 18px;
            font-size: 12px;
            color: #8f959e;
          }
          .weight_center {
            line-height: 22px;
            margin-top: 5px;
            color: #646a73;
          }
        }

        .ObjectiveItem_objective_content_right_score {
          margin-left: 6px;
          padding-right: 11px;
          min-height: 34px;
          line-height: 32px;
          border: 1px solid transparent;
          color: #646a73;
          background-color: inherit;
          width: 48px;
          text-align: right;

          .score_top {
            line-height: 18px;
            font-size: 12px;
            color: #8f959e;
          }

          .score_center {
            line-height: 22px;
            margin-top: 5px;
            color: #646a73;
            letter-spacing: 1px;
          }
        }
      }
      .ObjectiveItem_objective_content_right::after {
        content: "";
        display: block;
        position: absolute;
        bottom: 13px;
        left: -28px;
        border-left: 1px solid #e4e5e7;
        top: 18px;
      }
    }
    .ObjectiveItem_objective_bottom {
      position: relative;
      color: #8f959e;
      font-size: 12px;

      .down_svg {
        position: absolute;
        width: 24px;
        height: 24px;
        left: -28px;
        top: -14px;
        // transform: rotateX(180deg);
      }
    }
  }
  .drawer_content_wrap_container::after {
    content: "";
    display: block;
    position: absolute;
    left: 60px;
    bottom: 0;
    right: 24px;
    height: 1px;
    background: #dee0e3;
    z-index: 2;
  }
  .kr_list_wrap {
    li {
      padding: 0 22px 0 58px;
      .kr_result_content {
        position: relative;
        display: flex;
        padding: 12px 0;
        padding-left: 20px;
        border-bottom: 1px solid #dee0e3;
        .kr_result_content_center {
          flex: 1;
          color: #1f2329;
          span {
            color: #3370ff !important;
            cursor: pointer;
          }
        }
        .kr_result_content_right {
          display: flex;
          align-items: center;
          .right_progress {
            width: 77px;
            text-align: right;
            display: inline-block;
            color: #646a73;
            .progress_center {
              color: #646a73;
              white-space: nowrap;
              display: flex;
              align-items: center;
              justify-content: flex-end;

              span {
                display: inline-block;
                width: 43px;
              }
            }
          }
          .right_weight {
            color: #646a73;
            margin-left: 16px;
            width: 56px;
            text-align: right;
            padding: 0 8px;
          }
          .right_score {
            letter-spacing: 1px;
            margin-left: 6px;
            padding-right: 11px;
            color: #646a73;
            width: 48px;
            text-align: right;
          }
        }
      }
      .kr_result_content::before {
        content: " ";
        display: block;
        position: absolute;
        left: 2px;
        top: 19px;
        width: 6px;
        height: 6px;
        border-radius: 50%;
        background-color: #3370ff;
      }
      &:last-child .kr_result_content {
        border-bottom: 0px;
      }
    }
  }
  .drawer_content_wrap_progress {
    border-top: 1px solid #dee0e3;
    display: flex;
    .drawer_content_wrap_progress_left {
      width: 28px;
      height: 28px;
      line-height: 28px;
      margin: 12px 14px 12px 18px;
      background-color: #eff0f1;
      border-radius: 50%;
      color: #8f959e;
      text-align: center;
      font-size: 14px;
    }
    .drawer_content_wrap_progress_center {
      flex: 1;
      p {
        color: #1f2329;
        font-weight: 700;
        line-height: 26px;
        padding: 13px 0 4px;
      }
      div {
        line-height: 26px;
        padding-right: 15px;
        padding-bottom: 11px;
      }
    }
  }
}
</style>
