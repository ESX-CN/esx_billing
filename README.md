# esx_billing
FiveM基于ESX框架的账单系统

This resource for ESX adds possibility for different jobs to send bills to players, for example making police units able to give people fines. It comes with a menu for paying bills, to open the menu the default keybind is `F7`.

There is a developer server event available in order to register bills in the database, see default resources for examples.

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

# Legal
### License
esx_billing - billing for ESX

Copyright (C) 2015-2020 Jérémie N'gadi

This program Is free software: you can redistribute it And/Or modify it under the terms Of the GNU General Public License As published by the Free Software Foundation, either version 3 Of the License, Or (at your option) any later version.

This program Is distributed In the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty Of MERCHANTABILITY Or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License For more details.

You should have received a copy Of the GNU General Public License along with this program. If Not, see http://www.gnu.org/licenses/.
