# BUAAUpdateActionVer
the main python script is forked from https://github.com/windiboy/BUAAAutoUpdate

# Warning
**This repository is created just for learning, and everyone who use it should not violate relevant regulations.**

# How to use?
## Step 1
- Fork this repository to your own github account. (Of course you should log in first!!!)
- 第一次设置时请确保当天还未打卡
## Step 2
- 使用电脑端chrome浏览器，打开并登录[北航师生报平安系统](https://app.buaa.edu.cn/site/buaaStudentNcov/index)
- 如果无法获取定位，可以参考[Chrome 自定位置](https://blog.csdn.net/u010844189/article/details/81163438)。
- 按F12打开控制台(或右键->检查)，切换到网络栏（network）。在页面中填好全部信息之后，点击提交，然后不要退出页面，查看`network(网络)`，选择`全部`标签，点击下面`名称`中的`save`项。点击后查看右侧`Payload(载荷)`标签，点击`Form Data(表单数据)`右侧的`view source(查看源代码)`，全选复制备用（一天只有这一次机会，一定确保复制到粘贴板，强烈推荐复制后提前保存到某个文本文档）。
## Step 3
- Look above, click `Settings`->`Security`->`Secrets`->`Actions`->`New repository secret`, and add 4 action secrets as follow:
![BUAAAutoUpdateSecret.jpg](https://s2.loli.net/2022/07/05/pRWwYiA4Ovx2hBZ.jpg)
- The four names are: STUDENTID, PASSWORD, SERVER_SEC, FORM_DATA
- STUDENTID is your BUAA SSO Account ID, namely your student id.
- PASSWORD is the password of your BUAA SSO Account.
- SERVER_SEC is your Wechat_Key provided by [ServerChan](https://sct.ftqq.com/). If you don't have the key, please get one in ServerChan WeChat official account.
- FORM_DATA is got and saved from Step 2.
## Step 4
- Click `Action` above, and you are supposed to see the workflow named *BUAAAutoUpdate Action Ver*.
- This Action should be run manually for the first time, then it will run AUTOMATICALLY at the scheduled time EVERYDAY! Hurray!
![BUAAAutoUpdateAction.jpg](https://s2.loli.net/2022/07/06/upgEq81INAf7YyK.jpg)
- If you want to change the scheduled time, you can edit file ./.github/workflows/main.yml at line 12, it uses cron expression to set the schedule.
- If you don't know how to use cron expression, you can refer to [this page](https://help.aliyun.com/document_detail/64769.html).
- You can also make the schedule to be more stochastic by modifying the BUAAAutoUpdate.py Line 55 (**default: range 0 to 5 minutes**).
