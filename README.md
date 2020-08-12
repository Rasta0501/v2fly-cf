### fork 项目，点击Actions启用

   https://github.com/tlmoe/v2fly-cf

### 添加 Secrets

> CF_USER_IBM //账号
>
> CF_PASSWORD_IBM //密码
>
> CF_UUID_IBM #自行找UUID生成器生成
>
> CF_ORG_IBM #组织名
>
> CF_SPACE_IBM #空间名

- 组织和空间 名称： https://cloud.ibm.com/account/cloud-foundry
- cf_org: AwesomeApp
- cf_space: Development

![img](https://s1.ax1x.com/2020/08/12/avu1sK.png)

### 修改.github/workflows/deploy-to-ibm.yml

> IBM免费额度 256M
>
> 如果是部署到伦敦节点，修改api地址 cf_api: api.eu-gb.cf.cloud.ibm.com
>
> 建议修改schedule ，cron 格式参考 https://tool.lu/crontab/

### ~~修改 manifest-ibm.yml~~

### 登录ibm，查看项目域名

### 登录cloudflare，配置workers，可参考IBMYES



```
addEventListener(
  "fetch", event => {
    let url = new URL(event.request.url);
    url.host = "v2ws-comedic-dingo-ka.mybluemix.net";
    let request = new Request(url, event.request);
    event.respondWith(
      fetch(request)
    )
  }
)
```
