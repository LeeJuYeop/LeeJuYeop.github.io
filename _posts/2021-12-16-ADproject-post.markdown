---
layout: post
title:  "정렬알고리즘 시각화 프로그램"
description: SWP2 ADproject 발표
date:   2021-12-16 20:32:43 +0530
categories: Python
comments: true
---
소프트웨어프로젝트2 강의의 AD PROJECT 때 만든 정렬알고리즘 시각화 프로그램입니다.
배열의 원소(숫자)를 막대그래프로 나타낸 뒤 정렬 알고리즘을 선택하면 시각적으로 정렬 과정을 보여줍니다.

https://github.com/LeeJuYeop/-KMU-SWP2-2021-2-ADProject


# 프로젝트 진행 과정
같은 학교 이주원(20151334) 팀원님과 협업하여 제작하였으며 GUI 부분을 주로 맡아주셨습니다.
저는 정렬알고리즘을 구현하는 부분을 맡았습니다.

# GUI
PyQt5를 이용하여 GUI를 구성했습니다. 핵심 코드는 다음과 같습니다.

먼저 interval 간격으로 drawUI를 호출합니다.
```python
# timer: interval 간격으로 drawUI를 호출
  self.timer = QTimer()
  self.timer.start(self.drawConfig['interval'])
  self.timer.timeout.connect(self.drawUI)

  self.sort1 = Sort1()
  self.sort2 = Sort2()

  self.initUI()
  self.setEvents()
```

drawUI는 drawList를 토대로 그래프를 그립니다. 이 때 drawList는 정렬 알고리즘에서 배열의 순서가 바뀔 때마다 갱신됩니다.
```python
  def drawUI(self):
        if len(self.drawList) < 1: return
        if 'error' in self.drawList[0]:
            self.setText(self.drawList[0]['error'])
        if 'values' in self.drawList[0] and 'color' in self.drawList[0]:
            self.values = list(self.drawList[0]['values'])
            self.colors = self.drawList[0]['color']
            self.drawList.pop(0)
            self.update()
```

# 정렬 알고리즘
총 10개의 정렬 알고리즘을 구현했습니다.
* bogo 정렬
* bubble 정렬
* cocktail 정렬
* selection 정렬
* counting 정렬
* merge 정렬
* insert 정렬
* heap 정렬
* quick 정렬
* intro 정렬