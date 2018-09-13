# 共変量シフトのお試しプロジェクト

Covariate Shift下におけるデータへのsample weightの掛け方としては、カーネル法によるRuLSIFが有名。
but, ゴリゴリのチューニングが必要
- カーネルの選択
- カーネルのパラメータ(正規分布であれば、mean, sigma)

そこでもっと簡単に（カーネルを使わないで）できる方法として、information estimatorを使うことを考える。

## 1. cal_MCEW
`notebooks/cal_MCEW.ipynb`

information estimatorでの、重みを最適化することによるsample weightの設定を試したコード.

1次元での簡単な問題設定では動くことを確認。重みの最適化方法の考案も一応行っている。(勾配が最も大きい方向の重みを0にして、境界条件に垂直に射影するという方法)

## 2. compare_RULSIF.ipynb
`notebooks/compare_RuLSIF.ipynb`

RuLSIFとの精度比較を行ったコード

## 3. CS_XGB.ipynb
`notebooks/CS_XGB.ipynb`

XGBoostでのCovariate-Shift条件下での精度比較

## pyRULSIF.py
`src/pyRULSIF.py`
拝借したRuLSIF実装
