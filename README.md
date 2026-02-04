# Atlassian docker 部署 all in one
JIRA, Confluence, Bitbucket...从官方的docker源下载部署

Clone之后修改docker-compose.yml，注释掉不需要的容器，修改各个server.xml里的域名，然后 `docker compose up -d` 启动

Generating license:
```
java -jar /var/agent/atlassian-agent.jar -d -m {your_mail} -n {your_name} -o {your_org} -s {your_server_id} -p {product_bundle_id}
```
各产品对应的product_bundle_id：
```
Jira：jira
Confluence: conf
Bitbucket: stash
其他三方插件：在plugin管理中查看应用key
```

附上Jira的本地化jar，把大部分“问题”改成了“任务”