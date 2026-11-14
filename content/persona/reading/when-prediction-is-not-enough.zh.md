---
title: "模型预测得很准，为什么仍然不够？（2/3）"
subtitle: "准确率之所以有说服力，是因为它看起来很像理解，但两者并不是一回事。"
description: "从预测、机制和医疗模型迁移出发，思考一个成功模型为什么仍可能在环境变化后失效。"
date: 2026-11-14
draft: false
contentType: "reading-note"
sourceBook: "Scale"
sourceBookZh: "规模"
url: "/zh/persona/when-prediction-is-not-enough/"
translationUrl: "/persona/when-prediction-is-not-enough/"
translationLabel: "EN"
translationCta: "Read in English"
series: ["Persona", "AI 时代的《规模》"]
tags: ["AI", "医疗", "科学思维"]
provenanceStatus: "verified"
provenanceSources:
  - "https://www.penguinrandomhouse.com/books/314049/scale-by-geoffrey-west/"
  - "https://pubmed.ncbi.nlm.nih.gov/9082983/"
  - "https://doi.org/10.1214/10-STS330"
  - "https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1002683"
build:
  list: never
  render: always
---

几乎每个建模项目都会出现一个数字接管会议室的时刻。验证成绩比预期更好，曲线非常干净，一个原本混乱的问题突然像是得到了解决。

我很理解这种轻松。好的预测结果具体、可比较，也方便优化和辩护。但它同时诱惑我们进行一次安静的替换：模型预测得很好，所以模型理解了这个问题。

麻烦往往从这里开始。

## 《规模》为什么总在追问“为什么”

《规模》中最令人难忘的模式之一，是代谢率与体重之间的关系。在许多生物中，这个指数常被描述为接近四分之三。一个复杂的生命世界，似乎坍缩成了一条简单直线。

韦斯特并没有把这条线当成终点。他与 James Brown、Brian Enquist 尝试用空间填充的运输网络、相对恒定的终端单元和能量耗散最小化来解释这个指数。这套模型后来受到过讨论，而科学机制本来就应该接受讨论。它的价值不是结束争论，而是把假设暴露出来，让争论能够继续。

这就是机制在预测之外增加的东西：它给出规律可能持续的理由，推出其他应该观察到的现象，也指出规律可能在哪里失效。

拟合斜率告诉我们，某个关系曾经重复出现；机制追问它为什么会重复。

## 预测有自己正当的工作

这并不意味着预测在科学上低人一等。统计学家 Galit Shmueli 曾经区分预测与解释两种建模目标。一个变量可能帮助预测，却并不是原因；一个具有因果意义的因素，也可能不会明显提高短期预测准确率。

我们一直在使用没有完整机制解释的有效预测。天气预报不需要在每个温度数字旁边展开全部大气过程，垃圾邮件过滤器也不需要先建立一套人类欺骗理论。

真正困难的是判断：什么时候预测已经足够？

对于稳定、低风险的任务，反复出现的预测性能可能就是最重要的结果。但当模型跨医院使用、开始影响治疗，或者进入持续变化的环境，我们实际上是在要求模型“旅行”。昨天环境里的成绩，变成了对明天环境的承诺。

这个承诺需要的不只是准确率。

## 影像里藏着一家医院

2018 年一项跨医院的肺炎胸部 X 光研究，至今仍是很好的提醒。模型在不同医院系统之间并不能保持一致表现，同时还能够非常准确地识别一张影像来自哪家医院。

这个结果令人不安，因为模型可能因为多种理由同时做对。有些影像特征确实与疾病有关，另一些则可能来自设备、图像处理方式、患者选择或本地流程。预测结果里面，藏着一张产生这些数据的医院画像。

只要医院痕迹与结局继续相关，模型就可以表现得很好。换一个地方，捷径可能立刻失效。

模型并没有犯一个愚蠢错误。它只是完成了优化要求它做的事：利用训练环境中一切稳定信号。错误的假设属于我们。我们把模型在一个环境里的成绩，当成了它理解环境之外问题的证据。

## 准确率为什么像一种结束

我觉得这也是这个区别在情感上很难接受的原因。机制上的不确定性让人不舒服，因为它让项目保持开放；一个指标则提供了结束感。

AI 进一步放大了这种吸引力。现代系统能够吸收我们无法逐项检查的变量，发现没有预料到的交互，并以一种接近理解的速度和语气给出结果。界面越自然，我们越容易忘记，流畅与准确回答的仍然是窄问题。

模型可以告诉我们，一个人很像过去的高风险病例。但它不能自动告诉我们，采取干预后会发生什么、风险为什么形成，或者这种相似性换到另一家医院后是否还重要。

这不是在批评预测，而是在提醒我们正确命名它的工作。

## 我们观察到的是哪一种成功？

模型成功以后，我现在认为最有用的反应既不是完全相信，也不是仪式化地要求“可解释”。更好的做法是放慢一点，先判断这究竟是哪一种成功。

模型是在一个数据管线里识别了可重复模式，还是能够跨时间保持校准？它是否能迁移到另一家机构？所谓解释是在描述模型行为，还是现实机制？如果进行干预，原来的关系还会不会成立？

每个问题都需要不同的证据。

准确率是一项真实成果，只是它不会自动授权我们提出所有更强的结论。

我从《规模》中得到的更深启发，并不是每个模式都需要一条宏大的统一理论，而是只有理解支撑模式的条件，我们才能更好地判断它能走多远。预测告诉我们某件事曾经有效，机制帮助我们追问：世界变化以后，它为什么还应该继续有效？

## 参考资料

- Geoffrey West. [*Scale*](https://www.penguinrandomhouse.com/books/314049/scale-by-geoffrey-west/). Penguin Books.
- West GB, Brown JH, Enquist BJ. [A General Model for the Origin of Allometric Scaling Laws in Biology](https://pubmed.ncbi.nlm.nih.gov/9082983/). *Science*. 1997.
- Shmueli G. [To Explain or to Predict?](https://doi.org/10.1214/10-STS330). *Statistical Science*. 2010.
- Zech JR, et al. [Variable Generalization Performance of a Deep Learning Model to Detect Pneumonia in Chest Radiographs](https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1002683). *PLOS Medicine*. 2018.
