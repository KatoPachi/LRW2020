---
title: "Peer-Induced Fairness in Games"
AuthorYear: Ho2009
RQ: Do they have a drive to look to others who are in similar circumstances to evaluate their outcomes and judge whether they have been treated fairly?
Answer: |
    Laboraoty experiment in which subjects play two independent ultimatum games sequentially.
Result: |
    Peer-induced fairness between followers is two times stronger than distributional fairness between leader and follower.
---

# RQ

- 最後通牒ゲームを行うと利己的なモデルにおけるサブゲーム完全均衡が観察されない
  - 予想：リーダーはごくわずかなパイの一部をフォロワーに与えることを提案して、フォロワーはそれに同意する
  - 多くの実験：多くの提案はパイの30\%から40\%であり、パイの配分が低いほど提案を棄却する確率が高くなる
- この矛盾を解決するために、他者のペイオフを考慮するようなモデルが開発されてきた
  - Fehr and Schmidt: inequity aversion
  - Charness and Rabin: extend inequity aversion to incorporate reciprocity
  - これらのモデルはゲーム内の他者との比較によって生じるものであり、特定の人との比較ではない
- この研究は、自分と同じ状況に置かれた人との比較（**peer-induced fairness**）とそれ以外の人との比較（**distributional fairness concerns**）を区別して、社会比較ができる状況でpeer-induced fairnessが意思決定により強い影響を与えるかどうかを分析する。

## 実験アイデア

- 一人のリーダー（leader）と二人のフォロワー（first followerとsecond follower）がいて、リーダーは逐次的に各フォロワーと最後通牒ゲームを行う実験
  - Second followerは直前の最後通牒ゲームにおけるleaderの提案を（ノイズつきの）シグナルとして受け取れる
  - Second followerがpeer-induced fairnessを動機としていないならば、このシグナルは提案の受諾の意思決定に影響を与えない＝二つの最後通牒ゲームは全く同じ結果となるはず
  - Second followerがpeer-induced fairnessを動機としているならば、このシグナルは一番目のフォロワーの利得に関する情報を含んでいるので、提案の受諾の意思決定に影響を与えるはず
- 主な結果：受け取ったシグナルが高いほど、二番目の最後通牒ゲームにおける提案拒否率が高くなった
  - 二回目のゲームにおいて、leaderはsecond followerが受け取ったシグナルによって行動を変えている
  - 構造推定を行ったところ、**peer-induced fairnessのパラメータはdistributional fairnessの2倍以上になった**

# 理論モデル

第$i$回目の最後通牒ゲームにおける、leaderの提案を$s_i$とする。followerの行動は$a_i$であり、$a_i = 1$ならば提案を受諾したことを意味し、$a_i = 0$ならば提案を拒否したことを示す。

First followerの効用関数は
\begin{equation}
U_{F1}(s_1, a_1) =
\begin{cases}
    s_1 - \delta \max\{0,(\pi - s_1) - s_1\}   &\text{if}\quad a_1 = 1 \\
    0                                          &\text{if}\quad a_1 = 0
\end{cases}
\end{equation}
ここで$\delta$はfirst followerが不利な立場にあることを嫌う程度を示している。

Second followerの効用関数は
\begin{equation}
U_{F2}(s_2, a_2) =
\begin{cases}
    s_2 - \delta \max\{0,(\pi - s_2) - s_2\} - \rho \hat{p}(z) \max\{0,\hat{s}_1(z) - s_2\}   &\text{if}\quad a_1 = 1 \\
    0    &\text{if}\quad a_1 = 0
\end{cases}
\end{equation}
ここで、$z = s_1 + \epsilon$は一回目のゲームにおけるリーダーの提案に関するシグナルであり、$\epsilon$は平均ゼロのノイズ項である。
このシグナルを用いることで、二番目のフォロワーは提案を受諾する確率$\hat{p}(z) = P(a_1 = 1 | z)$と受諾したときの提案の期待値$\hat{s}_1(z) = E(s_1 | z, a_1 = 1)$を推測することができる。
また、follower同士の利得の比較でsecond followerが不利な立場にあることを嫌う程度を$\rho$とする。

Leaderの効用関数は
\begin{equation}
U_{Li}(s_i, a_i) =
\begin{cases}
    \pi - s_i - \delta \max\{0, s_i - (\pi - s_i)\}   &\text{if}\quad a_1 = 1 \\
    0                                                 &\text{if}\quad a_1 = 0
\end{cases}
\end{equation}
注意すべきことは二回目のゲームにおけるリーダーの効用関数はシグナル$z$の影響を受けるということである、すなわち、$U_{L2}(s_2, a_2 | z)$。

## 均衡分析

Formalな証明は論文に任せる。ここでは、シグナルが均衡上の行動にどのような影響を与えるかをまとめる。

1. **第二回目のゲームにおいて、均衡上の提案$s_2^*$はシグナル$\hat{s}_1(z)$の非増加関数である**
    - 二回目のゲームにおいて、leaderの効用関数は$s_2$の減少関数なので、leaderは$U_{F2} \ge 0$を満たすような最小の$s_2$を提案する。
    - Second followerの効用関数は$\hat{s}_1(z)$の非増加関数なので、効用の条件を満たす最小の$s_2$は増加する
    - Leaderは$s_1 = s_2$となるような提案をしたとする。このとき、second followerがpeer-induced fairnessを考慮していないならば、leaderの提案は均衡として成立する。しかしながら、second followerがシグナル$\hat{s}_1(z) > s_2$を受け取ったら、この提案は均衡ではなくなり、$s_2^* > s_1^*$となるはず。
2. __どのようなシグナルが送られても、leaderのオファーは必ず$s_2^* \ge s_1^*$となる__

# 実験の流れ

- セッション・ラウンドの構成
  - 実験は4セッション設けた。各セッションにおいて、実験参加者は15名から21名で構成されて、24回のゲームを行う
  - 各ラウンドでグループのメンバーはランダムに異なり、互いの素性はばれない
  - 各ラウンドで参加者はRED（leader）、BLUE1（first follower）、BLUE2（second follower）の役割をランダムに与えられる
  - 実験の通貨単位：1ポイント=\$0.01
- ゲームの流れ
  1. REDがBLUE1に金額$s_1 \in \{0, 1, 2, \ldots, 100\}$をオファーする
  1. BLUE1はそのオファーを見て受諾するかどうかを決める
  1. 離散一様分布に従う$z \in \{-20, -10, 0, 10, 20\}$から値と$s_1$を足したものをシグナルとして、BLUE2に送る。BLUE2は$s_1$を推測して回答する（当てたらボーナス10ポイント）
  1. REDがBLUE2に金額$s_2 \in \{0, 1, 2, \ldots, 100\}$をオファーする
  1. BLUE2はそのオファーを見て受諾するかどうかを決める

# 実験結果

## Reduced-form Results

![Result1](1009kato/95106126-10d59b80-0773-11eb-8e46-9ff88f57d36d.png)

- __Result 1: 各最後通牒ゲームの結果は過去の研究と一貫した結果となっている__
  - オファーの額が低いほど、提案拒否率は高くなる
  - 14.5以下のオファーをする人は3.5\%を下回る

![Result2](1009kato/95106736-dddfd780-0773-11eb-8adf-98b14fe29d71.png)

- __Result 2: 推測した$s_1$の額より自分へのオファー額が低いと、second followerの提案拒否率は極端に高くなる__
  - $P(a_2^{it} = 1) = F(\gamma_0^i + \gamma_1 s_2^{it} + \gamma_2 \max \{ \hat{s}_1^{it} - s_2^{it}, 0 \})$をロジット分析した結果、$\hat{\gamma}_2 = -0.024 (p < 0.05)$となった
  - First followerが同様のモチベーションを持っているかどうかを調べるために、$P(a_1^{it} = 1) = F(\gamma_0^i + \gamma_1 s_2^{it} + \gamma_2 \max \{ s_2^{it} - s_1^{it}, 0 \})$をロジット分析した。その結果、$\hat{\gamma}_2 = -0.01 (p = 0.58)$となった

![Result3](1009kato/95456757-c76f9100-09aa-11eb-9720-ade88c749ae1.png)

- __Result 3: Second followerが推測した$s_1$が高いほど、second followerへの提案額は大きくなる__
  - $s_2 - \hat{s}_1$はゼロまわりで分布している。すなわち、second followerへの提案額は推論に影響を受ける
  - $s_2^{it} = \alpha_0^i + \alpha_1 \hat{s}_1^{it}(z^{it})$を推定したところ、$\hat{\alpha}_1 = 0.09 (p = 0.00)$となった
  - first followerへの提案額とsecond followerへの提案額の中央値が等しいという帰無仮説をWilcoxon signed-rank one-sided testを行った結果、p値は0.03となった

## Structural Estimation

![SE1](1009kato/95459869-29ca9080-09af-11eb-8a0a-5ffedd720099.png)

- Let $x_i = (s_{i1}, s_{i2}, a_{i1}, s_{i2})$ be an observed data (group-time level), and let $\beta = (\delta, \rho, \sigma_1, \sigma_2, \lambda_1, \lambda_2)$ be a vector of unknown parameter.
- $\varphi_i(s_i)$: density function of normal distribution of $s_i$ with mean $s^*_i$ and variance $\sigma_i^2$.
- $P_1(\delta, \lambda_1) = F(U_{F1}(\delta)/\lambda_1)$, and $P_2(\delta, \rho, \lambda_2) = F(U_{F2}(\delta,\rho)/\lambda_2)$, where $F$ is a logistic distribution.
- The likelihood function is
\begin{equation}
  L(\beta; x_i) =
  \prod_i
  \varphi_1(s_1) \varphi_2(s_2)
  P_1(\delta, \lambda_1)^{a_1} (1 - P_1(\delta, \lambda_1))^{(1 - a_1)}
  P_2(\delta, \rho, \lambda_2)^{a_2} (1 - P_2(\delta, \rho, \lambda_2))^{(1 - a_2)},
\end{equation}
- __Result 4: 最も当てはまりがよいモデルはpeer-induced fairnessを含めたものであった。すなわち、second followerはpeer-induced fairnessをモチベーションとしていれている__
  - peer-induced fairness $\hat{\rho} = 1.746$、distributional fairness $\hat{\delta} = 0.501$
  - $(\pi - s_2) - s_2$の差が1ポイント増えたら、second followerの提案拒否確率は0.5\%上昇する
  - $\hat{s}_1(z) - s_2$の差が1ポイント増えたら、second followerの提案拒否確率は1.8\%上昇する

![SE2](1009kato/95461603-61d2d300-09b1-11eb-8ad4-a617d0c1fb57.png)

- Let $x_{it} = (s_1^{it}, s_2^{it}, a_1^{it}, a_2^{it})$ be an observed data (individual-time level).
- Let $T^i_L$, $T^i_{F1}$, $T^i_{F2}$ denote the sets of decision rounds during which $i$ is the leader, first follower and second follower.
- The likelihood function for group $g$ (self-interested if $g = 0$; otherwise $g = 1$) is
\begin{equation}
  L_g(\beta;x_{it}) =
  \prod_{t \in T^i_L} \varphi^g_1(s_1^{it}) \varphi^g_2(s_2^{it})
  \prod_{t \in T^i_{F1}} P^g_1(\delta, \lambda_1)^{a_1^{it}} (1 - P^g_1(\delta, \lambda_1))^{(1 - a_1^{it})}
  \prod_{t \in T^i_{F2}} P^g_2(\delta, \rho, \lambda_2)^{a_2^{it}} (1 - P^g_2(\delta,\rho, \lambda_2))^{(1 - a_2^{it})}
\end{equation}
- The estimated likelihood function is
\begin{equation}
L(\beta, \theta; x_{it}) = \prod_i [\theta L_0(\beta;x_{it}) + (1 - \theta) L_1(\beta; x_{it})]
\end{equation}

- __Result 5: 異質性を考慮すると、尤度関数の当てはまりがよくなる。すなわち、実験参加者の選好に大きな異質性がある__
  - 利己的な実験参加者はおよそ50\%

# Conclusions

> We examine two distinct kinds of fairness concerns: (i) distributional fairness concerns (relative to other players in game) and (ii) peer-induced fairness concerns (relative to one's peer). ... In combination, these [experimental] results strongly suggest the existence of peer-induced fairness. Finally, we show how peer-induced fairness plays a key role in several economic applications. For example, peer-induced fairness can restrict a monopoly's ability to price discriminate, account for the low variability in CEO compensation, and lead to the occurrence of labor strikes.
