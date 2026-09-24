# love-pressured-test
恋爱忍受压力值测试

## HTTP 网关自定义域名
迁移原因：使用自定义域名入口访问，避免继续依赖云开发默认访问地址；平台提示是否消失需部署后实际核验。
- 地址：https://sioyuan.site/pressured-quiz/
- 域名：sioyuan.site；触发路径：/pressured-quiz；资源类型：静态托管；选择现有实例 pressured-quiz；路径透传关闭。
- 先部署静态文件，再添加独立路由；保留现有根路由及其他站点。
- 仅在匹配网关路径时设置资源基路径，兼容末尾没有斜杠的 URL；保留根路径与本地预览。
- 题目、选项、计分、结果和浏览器存储未修改；没有新增后端接口或修改实际网关配置。
- 部署后验收带/不带末尾斜杠的路径，检查脚本、样式、答题和结果；代码不能绕过平台限制。
- 回滚：撤销本提交并重新部署，网关配置恢复原值。
官方说明：https://docs.cloudbase.net/service/access-static-hosting
