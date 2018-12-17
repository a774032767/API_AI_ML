# Product Requirements


| Target release | 11-30-2018 |
| ------ | ------ |
| Epic | 热水器声控调节app |
| Document Status | 未起头 |
| Document owner | 陈嘉劲 |
| Designer | 陈嘉劲 |
| Developer | 陈嘉劲 |
| QA | 陈嘉劲 |
| API | 百度语音识别API | 

## 专业术语：
* 信噪比：信噪比，英文名称叫做SNR或S/N（SIGNAL-NOISE RATIO)，又称为讯噪比。是指一个电子设备或者电子系统中信号与噪声的比例。这里面的信号指的是来自设备外部需要通过这台设备进行处理的电子信号，噪声是指经过该设备后产生的原信号中并不存在的无规则的额外信号（或信息），并且该种信号并不随原信号的变化而变化。

## 产品定位
* 智能热水器语音智能调节

## 产品背景
* 在不少80后，部分90后记忆中，普通百姓家基本是难觅热水器的踪影，浴池和自己烧水成为大部分人的选择。随着人民生活水平的不断提高，热水器已经成为了百姓家中必备的家电产品。如今，在洗澡的过程中，简化对热水器的控制使用，能带来更好的体验。智能化热水器在顺应时代的发展和需求中应运而生。

## 产品市场
* 在往年来热销的电热水器中，有一些值得关注的关键字，比如电脑式、遥控、速热、智能WiFi控制等。这些关键字中，还有一些是热水器的新增功能。其中“智能WiFi控制”这一关键字入围，根据奥维云网(AVC)提供的大数据显示，国内线下市场所售电热水器产品中，带有智能WiFi功能的热水器占比仅为12%，也就是仅有一成多的市场份额，智能热水器所占的热水器市场份额低。

## 用户痛点
* 使用热水器的时候不想伸手碰热冷水开关/去调水温
* 使用热水器的时候寻找合适温度时间过长
* 使用热水器的时候不受因水温所影响的舒适沐浴时间
* 使用热水器的时候想要调节水温，碰到冰冷的开关后手缩回去
* 调节水温的时候将热冷水开关左右调节，调节半天没找到自己想要的舒适的水温

## 解决问题
* 热水器想开就开想关就关
* 便捷用户调节水温  

## 目标用户
* 男女老少
* 懒惰的人
* 想要迅速获得准确水温的人

## 产品目标
* 热水器声控调节app能够帮助用户使用最简单地通过语音控制热水器

## 可用API
* 百度语音识别API （目前选用）
* 讯飞语音听写API

## 内容范围/主要功能

### 控制热水器开关
* 一声令下，热水器什么时候开启什么时候关闭由你决定

### 选择水温温度
* 想要什么水温就使用语音输入说出想要的水温温度，热水器将会将水温调节成对应温度

### 水温变热/冷
* 当前水温有点冷/热，根据预先设置，进行语音输入时说出让水温变热/冷一点的指示，水温将按照预设的数值上升/下降温度

## 核心价值
* 用户使用语音输入发送指令代替手动调节热冷水开关即可对热水器进行控制

## 出错原因/人工智能的概率性
* 导致用户在发出语音指令时没有执行的原因有

1. 语音过长
2. 语音录制环境被水声影响
3. 信噪比（电子设备或者电子系统中信号与噪声的比例）差，识别失败
4. 检测到人说话，但语音语速过快，语音过短

## 产品不做的事情
* 定时开关
* 延时调节水温

## 产品原型

### 首页

![首页](https://github.com/a774032767/API_AI_ML/blob/master/image/%E9%A6%96%E9%A1%B5.png)

### 连接

![连接](https://github.com/a774032767/API_AI_ML/blob/master/image/%E8%BF%9E%E6%8E%A5.png)

### 设置

![设置](https://github.com/a774032767/API_AI_ML/blob/master/image/%E8%AE%BE%E7%BD%AE.png)

  

## API 产品使用关键AI或机器学习之API的输出入展示


### 代码试例

* 代码试例1

```
from aip import AipSpeech

APP_ID = '15180100'
API_KEY = '4Lls6ixvcoB7lmacnLNKmH8f'
SECRET_KEY = 'LBlvF01tGMU6Bir2Vb4wjUXBwZCDXyws'

client = AipSpeech(APP_ID, API_KEY, SECRET_KEY)

# 读取文件
def get_file_content(filePath):
    with open(filePath, 'rb') as fp:
        return fp.read()

# 识别本地文件
client.asr(get_file_content('代码试例1.pcm'), 'pcm', 16000, {
    'dev_pid': 1536,
})


```
* 试例1结果

```
{
    "err_no": 0,
    "err_msg": "success.",
    "corpus_no": "15984125203285346378",
    "sn": "235C524F-23TR-562F-73DR-9157WOMR2A2H",
    "result": ["开启热水器"]
}
```

## 相关文档
* [产品原型](https://a774032767.github.io/API_AI_ML_app/index.html)
