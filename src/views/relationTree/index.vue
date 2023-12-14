<template>
  <div class="target-map-wrap">
    <!-- 右侧弹窗 -->
    <OkrTreeDetail
        :title="title"
        :visible="drawer"
        @closeDetailDrawer="closeDetailDrawer"
    ></OkrTreeDetail>
    <div class="relation-graph-wrap">
      <VueOkrTreeComponent
          :okrTreeData="okrTreeData"
          @showDetailDrawer="showDetailDrawer"
      ></VueOkrTreeComponent>
    </div>
  </div>
</template>

<script>
export default {
  name: "relationTree",
  components: {
    VueOkrTreeComponent: () => import("./components/myOkrTree/index.vue"),
    OkrTreeDetail: () => import("./components/okrTreeDetail.vue"),
  },
  data() {
    return {
      searchValue: "",
      tabList: [],
      okrTreeData: [{
        data: {
          right: [{
            id: 1,
            planName: '完成计划管理系统的设计、开发和应用',
            deptType: '0',
            charger: '许三领',
            percent: '80',
            budget: '90.25',
            children: [{
              id: 2,
              planName: '完成计划管理系统的设计、开发和应用',
              deptType: '1',
              charger: '许三领',
              percent: '80',
              budget: '90.25',
              children: [{
                id: 3,
                planName: '完成计划管理系统的设计、开发和应用',
                deptType: '2',
                charger: '许三领',
                percent: '80',
                budget: '90.25',
              }, {
                id: 4,
                planName: '完成计划管理系统的设计、开发和应用',
                deptType: '2',
                charger: '许三领',
                percent: '80',
                budget: '90.25',
              }, {
                id: 5,
                planName: '完成计划管理系统的设计、开发和应用',
                deptType: '2',
                charger: '许三领',
                percent: '80',
                budget: '90.25',
                children: [{
                  id: 6,
                  planName: '完成计划管理系统的设计、开发和应用',
                  deptType: '3',
                  charger: '许三领',
                  percent: '80',
                  budget: '90.25',
                }, {
                  id: 7,
                  planName: '完成计划管理系统的设计、开发和应用',
                  deptType: '3',
                  charger: '许三领',
                  percent: '80',
                  budget: '90.25',
                }, {
                  id: 8,
                  planName: '完成计划管理系统的设计、开发和应用',
                  deptType: '3',
                  charger: '许三领',
                  percent: '80',
                  budget: '90.25',
                  children: [{
                    id: 9,
                    planName: '完成计划管理系统的设计、开发和应用',
                    deptType: '4',
                    charger: '许三领',
                    percent: '80',
                    budget: '90.25',
                  }, {
                    id: 10,
                    planName: '完成计划管理系统的设计、开发和应用',
                    deptType: '4',
                    charger: '许三领',
                    percent: '80',
                    budget: '90.25',
                  }, {
                    id: 11,
                    planName: '完成计划管理系统的设计、开发和应用',
                    deptType: '4',
                    charger: '许三领',
                    percent: '80',
                    budget: '90.25',
                  }]
                }]
              }]
            }, {
              id: 12,
              planName: '完成计划管理系统的设计、开发和应用',
              deptType: '0',
              charger: '许三领',
              percent: '80',
              budget: '90.25',
              children: [{
                id: 13,
                planName: '完成计划管理系统的设计、开发和应用',
                deptType: '0',
                charger: '许三领',
                percent: '80',
                budget: '90.25',
              },{
                id: 14,
                planName: '完成计划管理系统的设计、开发和应用',
                deptType: '0',
                charger: '许三领',
                percent: '80',
                budget: '90.25',
              }
              ]
            },{
              id: 15,
              planName: '完成计划管理系统的设计、开发和应用',
              deptType: '0',
              charger: '许三领',
              percent: '80',
              budget: '90.25',
            }]
          }],
        }
      },
        {
          data: {
            right: [{
              id: 16,
              planName: '完成计划管理系统的设计、开发和应用',
              deptType: '0',
              charger: '许三领',
              percent: '80',
              budget: '90.25',
              children: [{
                id: 17,
                planName: '完成计划管理系统的设计、开发和应用',
                deptType: '1',
                charger: '许三领',
                percent: '80',
                budget: '90.25',
                children: [{
                  id: 18,
                  planName: '完成计划管理系统的设计、开发和应用',
                  deptType: '2',
                  charger: '许三领',
                  percent: '80',
                  budget: '90.25',
                }, {
                  id: 19,
                  planName: '完成计划管理系统的设计、开发和应用',
                  deptType: '2',
                  charger: '许三领',
                  percent: '80',
                  budget: '90.25',
                }, {
                  id: 20,
                  planName: '完成计划管理系统的设计、开发和应用',
                  deptType: '2',
                  charger: '许三领',
                  percent: '80',
                  budget: '90.25',
                  children: [{
                    id: 21,
                    planName: '完成计划管理系统的设计、开发和应用',
                    deptType: '3',
                    charger: '许三领',
                    percent: '80',
                    budget: '90.25',
                  }, {
                    id: 22,
                    planName: '完成计划管理系统的设计、开发和应用',
                    deptType: '3',
                    charger: '许三领',
                    percent: '80',
                    budget: '90.25',
                  }, {
                    id: 23,
                    planName: '完成计划管理系统的设计、开发和应用',
                    deptType: '3',
                    charger: '许三领',
                    percent: '80',
                    budget: '90.25',
                    children: [{
                      id: 24,
                      planName: '完成计划管理系统的设计、开发和应用',
                      deptType: '4',
                      charger: '许三领',
                      percent: '80',
                      budget: '90.25',
                    }, {
                      id: 25,
                      planName: '完成计划管理系统的设计、开发和应用',
                      deptType: '4',
                      charger: '许三领',
                      percent: '80',
                      budget: '90.25',
                    }, {
                      id: 26,
                      planName: '完成计划管理系统的设计、开发和应用',
                      deptType: '4',
                      charger: '许三领',
                      percent: '80',
                      budget: '90.25',
                    }]
                  }]
                }]
              }, {
                id: 27,
                planName: '完成计划管理系统的设计、开发和应用',
                deptType: '0',
                charger: '许三领',
                percent: '80',
                budget: '90.25',
                children: [{
                  id: 28,
                  planName: '完成计划管理系统的设计、开发和应用',
                  deptType: '0',
                  charger: '许三领',
                  percent: '80',
                  budget: '90.25',
                },{
                  id: 29,
                  planName: '完成计划管理系统的设计、开发和应用',
                  deptType: '0',
                  charger: '许三领',
                  percent: '80',
                  budget: '90.25',
                }
                ]
              },{
                id: 30,
                planName: '完成计划管理系统的设计、开发和应用',
                deptType: '0',
                charger: '许三领',
                percent: '80',
                budget: '90.25',
              }]
            }],
          }
        },
      ],
      defaultId: "",
      title: "",
      drawer: false,
    };
  },
  watch: {
    okrTreeData: {
      handler(newVal) {
        this.okrTreeData = newVal;
      },
      immediate: true,
      deep: true,
    },
  },
  mounted() {
  },
  methods: {
    showDetailDrawer() {
      this.drawer = true;
    },
    closeDetailDrawer() {
      this.drawer = false;
    },
  },
};
</script>

<style scoped lang="scss">
</style>
