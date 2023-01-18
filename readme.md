# 简介
抓取最新的油价信息，包括油价涨跌提醒（默认1小时更新一次数据）

数据源地址： http://www.qiyoujiage.com

# 安装
1 手动安装，两个文件夹分别 放入 <config directory> /custom_components 和 /packages目录,

并修改 packages/oilprice.yaml 文件内为自己本省拼音名字

如  region: shanghai

2 hacs安装 CUSTOM REPOSITORIES中填入：https://github.com/db-one/OilPrice-zui-xin-you-jia

# 配置
**Example configuration.yaml:**
```yaml
# 加载自定义配置文件
homeassistant:
  packages: !include_dir_named packages

```


# 前台界面
原始的界面是这样的

![avatar](https://github.com/aalavender/OilPrice/blob/master/2.PNG)

~~建议采用[markdown-mod](https://github.com/thomasloven/lovelace-markdown-mod )进行展示，效果是这样的~~
最新的Lovelace-ui已经集成了markdown控件，格式所有区别

![avatar](https://github.com/aalavender/OilPrice/blob/master/1.PNG)

新版的配置(直接编辑模式)：
```


<ha-icon icon="mdi:update"></ha-icon> {{ state_attr('sensor.zui_xin_you_jie', 'update_time')}} 
##  <center>92#<ha-icon icon="mdi:gas-station"></ha-icon>  <font color=#ea4335> {{ state_attr('sensor.zui_xin_you_jie', '92')}} </font>&nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;95#<ha-icon icon="mdi:gas-station"></ha-icon>  <font color=#fbbc05>  {{ state_attr('sensor.zui_xin_you_jie', '95')}} </font> <p> 98#<ha-icon icon="mdi:gas-station"></ha-icon> <font color=#4285f4>  {{ state_attr('sensor.zui_xin_you_jie', '98')}}</font>&nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; 0 # <ha-icon icon="mdi:gas-station"></ha-icon> <font color=#34a853>  {{ state_attr('sensor.zui_xin_you_jie', '0')}} </font></center> 
- {{ states('sensor.zui_xin_you_jie') }} 
- {{ state_attr('sensor.zui_xin_you_jie', 'tips')}}






<ha-icon icon="mdi:update"></ha-icon> {{ state_attr('sensor.zui_xin_you_jie', 'update_time')}} 
##  <center>92#<ha-icon icon="mdi:gas-station"></ha-icon>  <font color=#ea4335> {{ state_attr('sensor.zui_xin_you_jie', '92')}} </font>&nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;95#<ha-icon icon="mdi:gas-station"></ha-icon>  <font color=#fbbc05>  {{ state_attr('sensor.zui_xin_you_jie', '95')}} </font></center> 
- {{ states('sensor.zui_xin_you_jie') }} 
- {{ state_attr('sensor.zui_xin_you_jie', 'tips')}}



```
新版的配置(源代码编辑模式)：
```


type: markdown
content: >+
  <ha-icon icon="mdi:update"></ha-icon> {{ state_attr('sensor.zui_xin_you_jie',
  'update_time')}} 

  ##  <center>92#<ha-icon icon="mdi:gas-station"></ha-icon>  <font
  color=#ea4335> {{ state_attr('sensor.zui_xin_you_jie', '92')}} </font>&nbsp;
  &nbsp; &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;95#<ha-icon
  icon="mdi:gas-station"></ha-icon>  <font color=#fbbc05>  {{
  state_attr('sensor.zui_xin_you_jie', '95')}} </font> <p> 98#<ha-icon
  icon="mdi:gas-station"></ha-icon> <font color=#4285f4>  {{
  state_attr('sensor.zui_xin_you_jie', '98')}}</font>&nbsp;  &nbsp;  &nbsp; 
  &nbsp;  &nbsp;  &nbsp;  &nbsp; 0 # <ha-icon icon="mdi:gas-station"></ha-icon>
  <font color=#34a853>  {{ state_attr('sensor.zui_xin_you_jie', '0')}}
  </font></center> 

  - {{ states('sensor.zui_xin_you_jie') }} 

  - {{ state_attr('sensor.zui_xin_you_jie', 'tips')}}



type: markdown
content: >+
  <ha-icon icon="mdi:update"></ha-icon> {{ state_attr('sensor.zui_xin_you_jie',
  'update_time')}} 

  ##  <center>92#<ha-icon icon="mdi:gas-station"></ha-icon>  <font
  color=#ea4335> {{ state_attr('sensor.zui_xin_you_jie', '92')}} </font>&nbsp;
  &nbsp; &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;95#<ha-icon
  icon="mdi:gas-station"></ha-icon>  <font color=#fbbc05>  {{
  state_attr('sensor.zui_xin_you_jie', '95')}} </font></center> 

  - {{ states('sensor.zui_xin_you_jie') }} 

  - {{ state_attr('sensor.zui_xin_you_jie', 'tips')}}



```
