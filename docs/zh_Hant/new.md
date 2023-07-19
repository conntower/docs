---
layout: default
title: 更新細節
nav_order: 1
parent: 中文(繁體)
---

# 更新細節
{: .no_toc }

## 目錄
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# 1.6.0

## 新功能

### 搖杆

在橫屏狀態下，側邊控制欄的頂部已變更為搖杆控件，使用該控件可以簡單的在不使用浮動按鈕的情況下，完成隱藏側邊欄、屏幕管理、截圖、打開任務提醒頁面功能。

{: .note }
此功能旨在解決浮動按鈕在iOS風格UI狀態下不和諧，但部分功能只能通過浮動按鈕使用的問題而設計。用戶在隱藏浮動按鈕後可以通過該控件實現對應應用功能的調用，並且會具有更好的性能。將在iOS版本獨佔。

{: .important }
> 當前版本搖杆功能綁定為：
> - 左推：隱藏側邊欄 
> - 右推：顯示屏幕管理頁面 
> - 下拉：打開任務提醒頁面 
> - 上推：截圖 


演示截圖：
[]()

### 任務提醒

任務提醒頁面可由搖杆、浮動按鈕、工具頁進入。

首次使用時需要點擊右上角導入按鈕，進入導入數據源頁面可以看到兩個輸入框，用戶應當從兩個輸入框選擇其一填寫。

- URL輸入框內應填寫一個返回數據為json的http(s)的鏈接。其返回json的結構應當符合[該鏈接](https://conntower.github.io/data/json/CT_tasks.json)展示的結構。
- YAML或JSON輸入框應填入符合如下定义的内容：

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
  
完成填寫後，點擊右上角保存按鈕。任務提醒列表將自動刷新。

{: .note }
> 如果填写为URL时，该链接将被记忆，该次请求将被保存至本机，之后再次打开将直接读取本地保存数据，除非再次点击保存按钮将再次请求刷新页面。
> 
> 如果填写为YAML或JSON文本，该文本不会被记忆，但数据将保存在本机，之后再次打开将直接读取本地保存数据，除非再次填写该输入框并点击保存按钮将再次请求刷新页面。

{: .warning }    
> 在本地无数据时，填写内容不合法可能导致软件出错，下滑关闭任务提醒页重新进入即可。
> 
> 在本地有数据时，填写内容不合法可能导致软件出错，并且清除上次保存的任务提醒数据。

完成数据添加后，双击任务条目可添加任务提醒推送到设备，将在该任务设置时间后发送推送通知。
点击任务条目进入任务详情页，可查看任务详情。在任务详情页右上角点击置顶按钮可将该任务置顶，任务置顶状态会被记忆。

{: .important }
**导入数据源页面的成功保存操作会重置所有任务的置顶状态，请注意。**

## 功能变更

1. 长按首页任意非控制栏区域将取消控制栏的隐藏操作，如未隐藏则无效果。
2. 屏幕方向管理功能被统合，现在您可以在浮动按钮中呼出屏幕管理页。
3. 也可以在设置页中点击屏幕方向设置呼出屏幕方向设置页。

{: .fs-6 .fw-300 }
