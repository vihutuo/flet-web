---
slug: drag-and-drop-release
title: 'New release: Drag and Drop, absolute positioning and clickable container'
author: Feodor Fitsner
author_title: Flet founder and developer
author_url: https://github.com/FeodorFitsner
author_image_url: https://avatars0.githubusercontent.com/u/5041459?s=400&v=4
tags: [release]
---

We have just released [Flet 0.1.41](https://pypi.org/project/flet/0.1.41/) with drag-and-drop support and other neat features such as absolute positioning of controls inside stack and clickable container!

## Drag and Drop

Making drag-and-drop in Flet is a real joy - thanks to a smart drag-and-drop implementation in Flutter! You just have "draggable" control which could be dragged to a "drag target" which calls `on_accept` event handler when draggable is dropped.

<img src="/img/docs/controls/drag-and-drop/drag-and-drop-colors.gif" className="screenshot-50" />

Take a look at [Drag-and-Drop example](https://github.com/flet-dev/examples/blob/main/python/controls/drag-and-drop/drag-drop-colors.py).

Explore [`Draggable`](/docs/controls/draggable) and [`DragTarget`](/docs/controls/dragtarget) controls, their properties and events.

## Absolute positioning inside Stack

All visible controls now have `left` `top`, `right` and `bottom` properties to let them be absolutely positioned inside [`Stack`](/docs/controls/stack), for example:

```python {13-17}
import flet as ft

def main(page: ft.Page):

    page.horizontal_alignment = ft.CrossAxisAlignment.CENTER
    page.vertical_alignment = ft.MainAxisAlignment.CENTER

    page.add(
        ft.Container(
            ft.Stack(
                [
                    ft.Text("1", color=ft.colors.WHITE),
                    ft.Text("2", color=ft.colors.WHITE, right=0),
                    ft.Text("3", color=ft.colors.WHITE, right=0, bottom=0),
                    ft.Text("4", color=ft.colors.WHITE, left=0, bottom=0),
                    ft.Text("5", color=ft.colors.WHITE, left=40, top=35),
                ]
            ),
            border_radius=8,
            padding=5,
            width=100,
            height=100,
            bgcolor=ft.colors.BROWN_700,
        )
    )

ft.app(target=main)
```

<img src="/img/blog/drag-and-drop/absolute-positioned-numbers.png" className="screenshot-30" />

## Clickable container

[`Container`](/docs/controls/container) control has got `on_click` event which allows you to make a button from any control and with a beautiful material ripple effect when `ink` is set to `True`!

<img src="/img/docs/controls/container/clickable-container.gif" className="screenshot-70" />

See [source code](https://github.com/flet-dev/examples/blob/main/python/controls/container/clickable-container.py) for the example above.

[Give Flet a try](/docs) and [let us know](https://discord.gg/dzWXP8SHG8) what you think!

