---
layout: default
title: What's New
nav_order: 1
parent: English
permalink: /en/new
---

# What's New
{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# 2.0.0

## New Features

At this special time of the project's one-year anniversary, we are excited to share with you some major changes: we now offer a brand new design style on iPad, where the desktop mode is now the default; of course, we have also made similar optimizations for iPhone, and now we recommend using the new dot indicator button for operations.

### Dot Indicator Button

In desktop mode, a horizontal or vertical dot indicator will appear above or to the left of the main window. Clicking on it will pop up a menu, which can be used to restore the sidebar display or take screenshots. When desktop mode is turned off (i.e., in mobile mode), a vertical dot indicator will appear to the right of the main window when the device is in landscape orientation. Clicking on it will also pop up a menu, which can be used to hide or restore the sidebar, take screenshots, etc.

{: .note }
The dot indicator will completely replace the joystick and floating button in future versions.

Mobile Mode:

![6EFF2234-364F-488C-B56C-F31BC6D82BA1_1_102_o](https://github.com/conntower/docs/assets/24852023/358dfd68-d407-4381-9e80-be89f0cdbbcc)
![E1DB2B66-7671-4ECE-86DF-756F5BA53419_1_102_o](https://github.com/conntower/docs/assets/24852023/f1990172-0759-42ec-8fe6-f151f30b8eee)

Desktop Mode:

![CB7F36C3-B49D-4604-B76D-02EF0279E639_1_101_o](https://github.com/conntower/docs/assets/24852023/6a98d996-2687-465f-b1b2-ae9de75c47c5)

### Desktop Mode

A brand new UI designed for large-screen devices. In this mode, you can use a more powerful sidebar, and you can go to the page you need through the address bar. Above the address bar are buttons to hide the sidebar, go forward, go back, and reload, while below the address bar are buttons to load the homepage, tools, settings, and about.

{: .important }
In this mode, we have currently removed the double confirmation for the reload and homepage buttons.

![Simulator Screenshot - iPad Pro (12 9-inch) (6th generation) - 2023-11-21 at 10 26 53](https://github.com/conntower/docs/assets/24852023/fef663c3-5e2d-4d1b-9dba-6921ce12470e)

# 1.8.2

## New Features

### Dashboard

You can now open the dashboard directly on the home screen by pulling down the joystick or using the floating button. This is especially recommended for users with small screens when in landscape mode. In the dashboard, we've added a new tasks page where you can quickly add push notifications for tasks by clicking on them.

## Feature Changes

- The method for restoring the display of the sidebar has been changed. Instead of long-pressing anywhere on the interface, you can now simply shake your phone twice.
- The joystick pull-down function has been changed to open the dashboard.

# 1.8.0

## New Features

### Dashboard

Enable in settings. Once enabled, the Dashboard will be displayed at the top of the homepage. You can select the projects to display by swiping from the left side (on macOS, it can be scrolled). Currently, two projects are available: Album and Web Info.

#### Album

Displays the five most recent photos (from the entire photo album in the system). It is recommended to set the access permission to selected photos, so that only screenshots from this app will be displayed in the Dashboard. If you want to display photos from other apps, it is recommended to enable access to all photos.
In the album view, there are two buttons on the left sidebar: one for taking a screenshot of the current webpage 📷, and one for refreshing the album 🔄. If you have added other photos in the system photo album and want them to be displayed, click the refresh button.

#### Web Info

Displays the current webpage's request status code, URL.

# 1.7.0

## New Features

### Notification Management

Tools-Notification Management, click to enter the Notification Management page. It shows the notifications currently in the queue, and you can clear all notifications on this page.

### Layout Management

Settings-Layout Management, select the layout and return to apply it. You can freely combine layouts that contain joysticks and those that contain floating buttons.

### Theme

Settings-Theme, you can choose a dark or light theme, and the default is to follow the system. This feature is only valid during application startup and will return to default after the application is closed.

## Function Changes

The UI of the Tools, Settings, and About pages has been redesigned and now fully uses the design style after iOS 13. Function logic has been adjusted, and list items that do not navigate to the secondary page will no longer display arrow indicators at the end. Input pages no longer appear in dialog boxes and all use standard design styles. 

# 1.6.0

## New Features

### Joystick

In landscape mode, the top of the side control bar has been changed to a joystick widget. This widget allows you to easily hide the side bar, manage screens, take screenshots, and open the task reminder page without using a floating button.

{: .note }
This feature is designed to address the issue of the floating button not harmonizing with the iOS-style UI and the limitations of certain functions that can only be accessed through the floating button. After hiding the floating button, users can use this joystick widget to access the corresponding app functions, which will provide better performance. This feature is exclusive to the iOS version.

{: .important }
> The current joystick functionality is mapped as follows:
>   - Left swipe: Hide the sidebar
>   - Right swipe: Show the screen management page
>   - Pull down: Open the task reminder page
>   - Swipe up: Take a screenshot

Screenshot demonstration:

![](../../docs/assets/images/joystick.gif)

### Task Reminder

The task reminder page can be accessed through the joystick, floating button, or tools page.

When using it for the first time, click the import button in the upper right corner to enter the import data source page. On this page, you will see two input fields, and you should choose one of them to fill in.

- In the URL input field, enter a http(s) link that returns data in JSON format. The JSON structure returned by the link should match the structure displayed in [this link](https://conntower.github.io/data/json/CT_tasks.json).

- In the YAML or JSON input field, enter the content that conforms to the following definitions:

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

After filling in the content, click the save button in the upper right corner. The task reminder list will be automatically refreshed.

Screenshot demonstration:

![](../../docs/assets/images/reminder.gif)

{: .note }
> If you fill in the URL field, the link will be remembered, and the request will be saved locally. The next time you open it, the data will be directly loaded from the local storage, unless you click the save button again to refresh the page.
>
> If you fill in the YAML or JSON text, the text will not be remembered, but the data will be saved locally. The next time you open it, the data will be directly loaded from the local storage, unless you fill in the input field again and click the save button to refresh the page.

{: .warning }
> If there is no data locally, filling in invalid content may cause errors in the software. In such cases, simply swipe down to close the task reminder page and reopen it.
>
> If there is existing data locally, filling in invalid content may cause errors in the software and clear the previously saved task reminder data.

After adding the data, double-clicking on a task item will add a task reminder that will be sent as a push notification to the device after the set time for the task.
Clicking on a task item will navigate to the task details page, where you can view the task details. Clicking the pin button in the upper right corner of the task details page will pin the task to the top. The pinned status of the task will be remembered.

{: .important }
**Note that successfully saving the data on the import data source page will reset the pinned status of all tasks. Please be aware of this.**

## Functional Changes

1. Long-pressing any non-control area on the home page will cancel the hiding operation of the control bar if it is not already hidden.
2. The screen orientation management feature has been integrated, and you can now bring up the screen management page from the floating button.
3. You can also access the screen orientation settings by clicking on the screen orientation setting in the settings page.

{: .fs-6 .fw-300 }
