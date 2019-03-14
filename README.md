# esx_billing
FiveM基于ESX框架的账单系统
## 下载 & 安装

### 使用 Git
```
cd resources
git clone https://github.com/ESX-CN/esx_billing [esx]/esx_billing
```

### 手动
- 下载 https://github.com/ESX-CN/esx_billing/archive/master.zip
- 将它解压至 `[esx]` 目录


## 安装
- 导入 `esx_billing.sql` 至你的数据库
- 添加如下至你的 `server.cfg`:

```
start esx_billing
```

## 使用教程
按 `[F7]` 打开账单菜单

```lua
local amount                         = 100
local closestPlayer, closestDistance = ESX.Game.GetClosestPlayer()

if closestPlayer == -1 or closestDistance > 3.0 then
	ESX.ShowNotification('There\'s no players nearby!')
else
	TriggerServerEvent('esx_billing:sendBill', GetPlayerServerId(closestPlayer), 'society_taxi', 'Taxi', amount)
end
```
