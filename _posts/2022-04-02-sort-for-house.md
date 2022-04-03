---
layout:     post

title:      "Program for House"

subtitle:   " Sort "

date:       2022-04-02 17:42:00

author:     "Zz"

header-img: "img/default-bg.jpeg"

catalog: true

tags:

    - daily


---

daily|

# Intro

买新房时不知如何选择，所以就自己写了个程序，用来根据不同要素进行打分排序，在选房时不再盲目焦虑。

```python
import sys
import math

NUMBER = [11, 12, 15, 16, 42, 43, 54, 55, 56, 57, 58, 59, 64, 65]
NUM_TO_SCORE = {6:9, 7:1, 12:1, 17:1, 18:1, 19:1, 22:1}
TYPE_TO_SCORE = {"A1":10, "A2":10, "B1":8, "B2":8, "C1":6, "C2":6}
FLOOR = [x for x in range(1, 17)]
TYPE = ["A", "B", "C"]
WEIGHT = {"num_to_score":0.4, "floor_to_score":0.3, "type_to_score":0.3}


def get_score(info):
  score = 0
  for key in WEIGHT.keys():
    score += WEIGHT[key] * info[key]
  return score

def sort():
  info = {}
  info_list = []
  num_build = 0
  type_list = []
  FLOOR_TO_SCORE = {}
  for f in FLOOR:
    FLOOR_TO_SCORE[f] = 15 - abs(15 - f)
  for n in NUMBER:
    if n == 11 or n == 12:
      num_build = 7
      type_list = ["B1", "A2", "A1", "B2"]
    if n == 15 or n == 16:
      num_build = 6
      type_list = ["B1", "A2", "A1", "B2"]
    if n == 42 or n == 43:
      num_build = 12
      type_list = ["B1", "C2", "A1", "B2"]
    if n == 54 or n == 55:
      num_build = 17
      type_list = ["A1", "B2", "B1", "A2"]
    if n == 56 or n == 57:
      num_build = 18
      type_list = ["A1", "B2", "B1", "A2"]
    if n == 58 or n == 59:
      num_build = 19
      type_list = ["A1", "B2", "B1", "A2"]
    if n == 64 or n == 65:
      num_build = 22
      type_list = ["A1", "B2", "B1", "C2"]

    for f in FLOOR:
      for t in type_list:
        info["number"] = n
        info["type"] = t
        info["floor"] = f
        info["num_to_score"] = NUM_TO_SCORE[num_build]
        info["floor_to_score"] = FLOOR_TO_SCORE[f]
        info["type_to_score"] = TYPE_TO_SCORE[t]
        info["score"] = get_score(info)
        info_list.append(info)
  info_list = sorted(info_list, key = lambda s:s["score"])
  return info_list


if __name__ == '__main__':
  info_list = sort()
  print(info_list)
```



