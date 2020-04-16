<template>
  <div style="width:100vw;height:200vh" @click="onContextmenu">{{message}}</div>
</template>

<script>
export default {
  data() {
    return {
      message: "左键打开菜单"
    };
  },
  methods: {
    onContextmenu(event) {
      this.$contextmenu({
        items: [
          {
            label: "返回(B)",
            onClick: () => {
              this.message = "返回(B)";
              return true;
            }
          },
          {
              label: "前进(F)", disabled: true,
              onClick: () => {
              this.message = "返回(B)";
              return true;
            }
          },
          { label: "重新加载(R)", divided: true, icon: "el-icon-refresh" ,
              onClick: () => {
              this.message = "返回(B)";
              return true;
          }},
          { label: "另存为(A)..." ,
              onClick: () => {
              this.message = "返回(B)";
              return true;
          }},
          { label: "打印(P)...", icon: "el-icon-printer" ,
              onClick: () => {
              this.message = "返回(B)";
              return true;
          }},
          { label: "投射(C)...", divided: true,
              onClick: () => {
              this.message = "返回(B)";
              return true;
          } },
          {
            label: "使用网页翻译(T)",
            divided: true,
            minWidth: 0,
            children: [{ label: "翻译成简体中文",
              onClick: () => {
              this.message = "返回(B)";
              return true;
          } }, { label: "翻译成繁体中文",
              onClick: () => {
              this.message = "返回(B)";
              return true;
          } }]
          },
          {
            label: "截取网页(R)",
            minWidth: 0,
            children: [
              {
                label: "返回(B)",
                onClick: () => {
                  this.message = "返回(B)";
                  console.log("返回(B)");
                  return true;
                }
              },
              { label: "前进(F)", disabled: true ,
                  onClick: () => {
                  this.message = "返回(B)";
                  return true;
              }},
              { label: "重新加载(R)", divided: true, icon: "el-icon-refresh",
                  onClick: () => {
                  this.message = "返回(B)";
                  return true;
              } },
              { label: "另存为(A)...",
                  onClick: () => {
                  this.message = "返回(B)";
                  return true;
              } },
              { label: "打印(P)...", icon: "el-icon-printer",
                  onClick: () => {
                  this.message = "返回(B)";
                  return true;
              } },
              { label: "投射(C)...", divided: true,
                  onClick: () => {
                  this.message = "返回(B)";
                  return true;
              } },
              {
                label: "使用网页翻译(T)",
                divided: true,
                minWidth: 0,
                children: [
                  { label: "翻译成简体中文",
                      onClick: () => {
                      this.message = "返回(B)";
                  return true;
              } },
                  { label: "翻译成繁体中文" ,
                      onClick: () => {
                      this.message = "返回(B)";
                      return true;
                  }}
                ]
              },
              {
                label: "截取网页(R)",
                minWidth: 0,
                children: [
                  {
                    label: "截取可视化区域",
                    onClick: () => {
                      this.message = "截取可视化区域";
                      console.log("截取可视化区域");
                      return true;
                    }
                  },
                  { label: "截取全屏" ,
                      onClick: () => {
                      this.message = "返回(B)";
                      return true;
                  }}
                ]
              },
              { label: "查看网页源代码(V)", icon: "el-icon-view",
                  onClick: () => {
                  this.message = "返回(B)";
                  return true;
              } },
              { label: "检查(N)" ,
                  onClick: () => {
                  this.message = "返回(B)";
                  return true;
              }}
            ]
          },
          { label: "查看网页源代码(V)", icon: "el-icon-view" ,
              onClick: () => {
              this.message = "返回(B)";
              return true;
          }},
          { label: "检查(N)",
              onClick: () => {
              this.message = "返回(B)";
              return true;
          } }
        ],
        event,
        customClass: "class-a",
        zIndex: 3,
        minWidth: 230
      });
      event.preventDefault();
    }
  }
};
</script>