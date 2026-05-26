# my-openwrt-brutal
记录一系列瞎折腾

1、本地系统
iStoreOS 24.10.6 2026041710（内核：6.6.127） X86
下载brutal插件：https://github.com/phuslu/tcp-brutal/releases/tag/v1.0.1
选择brutal_linux_amd64
上传到openwrt，赋予运行权限，并运行。
本地安装sing-box 最新版
修改节点对应的配置文件
"flow": "",
"multiplex": {
        "enabled": true,
        "protocol": "smux",
        "max_connections": 4,
        "min_streams": 4,
        "padding": false,
        "brutal": {
        "enabled": true,
        "up_mbps": 50,   #自行修改
        "down_mbps": 50   #自行修改
        }
      }
2、服务器VPS
X86的VPS，使用八合一脚本中的，安装bbr选项，进入选择编译安装brutal
服务器端使用八合一脚本安装sing-box
sing-box配置所在目录 /etc/v2ray-agent/sing-box/conf/config
编辑vless节点配置
"flow": "", 
....  ....
 "multiplex": {
        "enabled": true,
        "padding": false,
        "brutal": {
          "enabled": true,
          "up_mbps": 50,   #自行修改
          "down_mbps": 50  #自行修改
            }
      }

备注：
1、openwrt必须安装brutal
2、singbox的配置文件必须"flow": "", 
3、客户端/服务器端 设置上传下载速度，且要对等
结论：对于甲骨文的免费VPS 没啥卵用

          






