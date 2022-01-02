# Algorithmic-Trading-ML
Establish a baseline trading bot, enhance the existing trading signals with machine learning algorithms.

---

Dataset 2015-04-02 to 2017-01-22.
Baseline model split only first 3 months for training, and the remainder for testing. SMA windows were 4/100 days.

<pre>
Cumulative Return (2021-01-22)
      Actual    Strategy
    1.386976	1.517607    Baseline:   3 months train, SMA 4/100
    1.464098	1.642728    Tune:       24 months train, SMA 4/100
    1.442623	1.056894    Tune:       24 months training, SMA 10/90
    1.606148	1.691820    Tune:       12 months train, SMA 4/80
</pre>
| ![Baseline](Baseline_actual_vs_strategy.png) | ![24-Month Training](Train_actual_vs_strategy.png) |
![SMA 10/90, 24-Month Training](Train_SMA_actual_vs_strategy.png)
![SMA 4/80, 6-Month Training](Train6_SMA_4-80_actual_vs_strategy.png)

---
Between Baseline and Tune 1, the classification report showed an accuracy improvment from .71 to .72, and the cumulative return increased from 1.51 to 1.64, so increasing the training window was worthwhile.

Tune 2 proved not worthwhile, with the classification report showing accuracy dropped to .54 and the cumulative return was sharply down at 1.05.

Tune 3 accuracy recovered to .56, and cumulative return peaked at 1.69, so this is the model I would pursue.
