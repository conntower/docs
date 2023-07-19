---
layout: default
title: 更新详情
nav_order: 1
parent: 中文(简体)
---

# 更新详情
{: .no_toc }

## 目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 1.6.0

### 新功能

### 摇杆

在横屏状态下，侧边控制栏的顶部已变更为摇杆控件，使用该控件可以简单的在不使用浮动按钮的情况下，完成隐藏侧边栏、屏幕管理、截图、打开任务提醒页功能。

{: .note }
此功能旨在解决浮动按钮在iOS风格UI状态下不和谐，但部分功能只能通过浮动按钮使用的问题而设计。用户在隐藏浮动按钮后可以通过该控件实现对应用功能的调用，并且会具有更好的性能。将在iOS版本独占。

{: .important }
> 当前版本摇杆功能绑定为：
>   - 左推：隐藏侧边栏
>   - 右推：显示屏幕管理页
>   - 下拉：打开任务提醒页
>   - 上推：截图

演示截图：
[]()

### 任务提醒

任务提醒页可由摇杆、浮动按钮、工具页进入。

首次使用时需要点击右上角导入按钮，进入导入数据源页面可以看到两个输入框，用户应当从两个输入框选择其一填写。

- URL输入框内应填写一个返回数据为json的http(s)的链接。其返回json的结构应当符合[该链接](https://conntower.github.io/data/json/CT_tasks.json)展示的结构。
- YAML或JSON输入框应填入符合如下定义的内容：

  JSON:
  ```json
    {
        "items": [
            {
                "id": "1",
                "title": "Demo 1",
                "time": "00:15:00",
                "description": "This is a demo task.",
                "tag": "Demo"
            },
            {
                "id": "2",
                "title": "Demo 2",
                "time": "00:30:00",
                "description": "This is a demo task.",
                "tag": "Demo"
            }
        ]
    }
  ```
  
  YAML
  ```yaml
  - id: '1' # id must have a maximum length of 3
    title: Demo 1 # title must have a maximum length of 20
    time: 00:15:00 # time must have a format as this one
    description: This is a demo task. # description must have a maximum length of 200
    tag: Demo # tag must have a maximum length of 20
  - id: '2'
    title: Demo 2
    time: 00:30:00
    description: This is a demo task.
    tag: Demo
  ```
  
完成填写后，点击右上角保存按钮。任务提醒列表将自动刷新。

{: .note }
> 如果填写为URL时，该链接将被记忆，该次请求将被保存至本机，之后再次打开将直接读取本地保存数据，除非再次点击保存按钮将再次请求刷新页面。
> 
> 如果填写为YAML或JSON文本，该文本不会被记忆，但数据将保存在本机，之后再次打开将直接读取本地保存数据，除非再次填写该输入框并点击保存按钮将再次请求刷新页面。

{: .warning }    
> 在本地无数据时，填写内容不合法可能导致软件出错，下滑关闭任务提醒页重新进入即可。
> 
> 在本地有数据时，填写内容不合法可能导致软件出错，并且清除上次保存的任务提醒数据。

完成数据添加后，双击任务条目可添加任务提醒推送到设备，将在该任务设置时间后发送推送通知。
点击任务条目进入任务详情页，可查看任务详情。在任务详情页右上角点击置顶按钮可将该任务置顶，任务置顶状态会被记忆，但导入数据源页面的成功保存操作会重置所有任务的置顶状态，请注意。

### 功能变更

1. 长按首页任意非控制栏区域将取消控制栏的隐藏操作，如未隐藏则无效果。
2. 屏幕方向管理功能被统合，现在您可以在浮动按钮中呼出屏幕管理页。
3. 也可以在设置页中点击屏幕方向设置呼出屏幕方向设置页。

{: .fs-6 .fw-300 }
