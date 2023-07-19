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
[]()

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
