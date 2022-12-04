# 简介
抓取最新的油价信息，包括油价涨跌提醒（默认8小时更新一次数据）

数据源地址： http://www.qiyoujiage.com

# 安装
1 手动安装，放入 <config directory>/custom_components/ 目录
  
2 hacs安装 CUSTOM REPOSITORIES中填入：https://github.com/aalavender/OilPrice

# 配置
**Example configuration.yaml:**
```yaml
sensor:
  - platform: oilprice
    name: 最新油价
    region: shandong
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
##  <center>92#<ha-icon icon="mdi:gas-station"></ha-icon>  <font color=#ea4335> {{ state_attr('sensor.zui_xin_you_jie', '92')}} </font>&nbsp; &nbsp; &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;95#<ha-icon icon="mdi:gas-station"></ha-icon>  <font color=#fbbc05>  {{ state_attr('sensor.zui_xin_you_jie', '95')}} </font> <p> 98#<ha-icon icon="mdi:gas-station"></ha-icon> <font color=#4285f4>  {{ state_attr('sensor.zui_xin_you_jie', '98')}}</font>&nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; 0#柴<ha-icon icon="mdi:gas-station"></ha-icon> <font color=#34a853>  {{ state_attr('sensor.zui_xin_you_jie', '0')}} </font></center> 
- {{ states('sensor.zui_xin_you_jie') }} 
- {{ state_attr('sensor.zui_xin_you_jie', 'tips')}}


```
新版的配置(源代码编辑模式)：
```


type: markdown
content: >
  <ha-icon icon="mdi:update"></ha-icon> {{ state_attr('sensor.zui_xin_you_jie',
  'update_time')}} 

  ##  <center>92#<ha-icon icon="mdi:gas-station"></ha-icon>  <font
  color=#ea4335> {{ state_attr('sensor.zui_xin_you_jie', '92')}} </font>&nbsp;
  &nbsp; &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;95#<ha-icon
  icon="mdi:gas-station"></ha-icon>  <font color=#fbbc05>  {{
  state_attr('sensor.zui_xin_you_jie', '95')}} </font> <p> 98#<ha-icon
  icon="mdi:gas-station"></ha-icon> <font color=#4285f4>  {{
  state_attr('sensor.zui_xin_you_jie', '98')}}</font>&nbsp;  &nbsp;  &nbsp; 
  &nbsp;  &nbsp;  &nbsp;  &nbsp; 0#柴<ha-icon icon="mdi:gas-station"></ha-icon>
  <font color=#34a853>  {{ state_attr('sensor.zui_xin_you_jie', '0')}}
  </font></center> 

  - {{ states('sensor.zui_xin_you_jie') }} 

  - {{ state_attr('sensor.zui_xin_you_jie', 'tips')}}


```
