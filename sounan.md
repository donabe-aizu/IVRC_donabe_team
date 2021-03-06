###### tags: `IVRC`
# 遭難体験企画書

## はじめに
このHackMDではIVRC土鍋チームの候補アイデア「遭難体験」の企画を検討する。  

以下を目指しています。
- インタラクティブな作品
- 今までのIVRCの作品内容にかぶらないもの
- チャレンジが求められる

企画書審査のポイント：**チャレンジの魅力と、その達成のための道筋の明確さ**

## 現在悩んでいる点(色んな人と相談がしたい)
- 足裏ディスプレイ
    - 実装したいこと
        - 悪路感(でこぼこ感)
        - 斜面感
    - 提示方法
        - ソレノイド
        - シリンダー
        - 足つぼマット
    - 問題
        - 人間の体重に耐えられるか？
        - 斜面感提示は難しい
        - 値段が高い
- ポンプ
    - 水を汲み上げる(吸い上げる)
    - 汲み上げ力が強いやつは値段が高い
    - 重力的にきつそうなら、タンクの位置を高くするしかない？
- 移動方法
    - モーショントラッキング
        - 体の動きの詳細に合わせて制御可能
    - 加速度センサ
        - 細かい動きには対応できるか微妙だが、足の上下の判断くらいはできそう
- タンク
    - 地面にタンクを置くのは重力的にきついか？

---

以下、企画書に書く内容

## 企画の目的
山における遭難がここ二十年増加傾向
https://www.npa.go.jp/publications/statistics/safetylife/chiiki/R02sangakusounan_gaikyou.pdf

- 登山の過酷さを伝えたい
- 気軽に行くべきではない
- 準備の大切さ
- 近場、低い山、その油断が一番危ない

増加原因
- 登山者が減少しているのにも関わらず、増加している
- 登山者の高齢化
- 近年は近場、低山
    - コロナ禍の体力低下
    - 油断
        - 地図やライトを持たない
        - 服装や装備も適当
        - 計画を立てていない

ゲーム性を取り入れる

- ハラハラ
- 普通のゲームと違って実際の体にフィードバックがある
- 楽しみつつ山の厳しさを知ってもらえる

## 制作物の概要と完成予想図
- 遭難というなかなか経験できないものを高い没入感で体験できる
- 疲労感や低体温症、山道の過酷さなどを体験
- ゲームでの自分の行動が体にフィードバック
- 全身、五感を使って楽しむ

<img src="https://i.imgur.com/m8lDrXT.jpg" width="400">

## ストーリー
近所の少し小高い山に登山に来ていたあなたはそんなに高い山ではないからとラフな格好で特に準備をせずに来ていた。徐々に暗くなりそろそろ戻ろうと思い、スマホを取り出した時、  
「あっ！」  
手を滑らせてスマホを落としてしまった！！  
そしてなんと運の悪いことに崖下に落ちてしまった...  
地図も懐中電灯もスマホで済ましていたあなたは絶体絶命に追い込まれる。

## コンテンツ内容詳細
### 概要
- 真っ暗で視界が狭い中、山を探索する。
- 様々な危険を回避しつつ、ゴールである山小屋を目指す。

### 疲労度
- 時が経つにつれて増加
- MAXになるとゲームオーバー
- 飲み物、食べ物で増加停止
- **ゲージなどを用意するのでは無く、五感で疲労を感じてもらう**

#### 疲労による影響
- 進む距離、速さが遅くなる
- 実際とVR内で違いを作る

### イベント
- 真横が崖
    - 石を投げて音で崖かそうでないか判断
- 野生動物
    - シカ
    - クマ
- 霧が一気に濃くなる
- でかい岩
    - 足を大きくあげる必要がある

### プレイヤーの操作
移動・・・足踏み  
ものを掴む・・・コントローラー掴むボタン  
アイテム使用・・・コントローラー  

## システム構成

### 必須なもの
- HMD
- ヘッドホン
- モーショントラッキング
- 疲労演出タンク
- 低体温症スーツ
- 手足の震え

### 全体

### HMD
- 時間は夜で霧も発生しているので、ほとんど見えない
- 疲労度に応じて、ピントが合わなくなり、視界がぼやける
- 視野が狭くなる
- 最終的には真っ暗になる

### ヘッドホン
- 野生動物や木々の音で臨場感演出
- 疲労度に応じて聴力が鈍る
- 最終的には心臓の音が大きく聞こえる

### 移動
モーショントラッキング
- 足の動きの詳細に合わせて制御可能
- 足を大きく上げることで岩を登る事ができるとか

### 疲労演出
- 疲れると体が重くなり、節々が痛くなってくる
- ↑を再現するシステム
- リュックのように背中にタンクを背負う
- ゲームの進行状況に応じて増加、減少

ポンプの実装  
地面からではなくラックとかを使ってある程度高い位置からなら弱い力のポンプでもいける？  
https://knkomko.hatenablog.com/entry/2019/10/01/193804

### 低体温症演出
#### 体温低下
- **チューブが張り巡らされたスーツ**
    - 水は上記のタンクの水を使う
- ファン付きベスト
- マイコン温度制御
- 冷却ベスト
    - 既製品を使う
    - 何で制御する？

#### 手の震え
- 手首、足首にバイブレーションするなにか(joy-conとか)をリストバンドなどで装着

### 悪路感提示
- 足裏ディスプレイ

http://www.res.kutc.kansai-u.ac.jp/~yone/research/pdf_graduate_thesis/201803g_HUANG_Xunda.pdf

http://www.soumu.go.jp/main_content/000323209.pdf

### 斜面感提示
- 足裏ディスプレイ

固定できるシーソー  
車とかあげるやつ

靴に空気で膨らむ袋を取り付ける

### 草むら感
- ふくらはぎとかに電気流す
- 扇風機でぴらぴら
- 

## 使用機材
- HMD(Quest2?)
- ヘッドホン
- PC
- ラズパイ
- ESP32
- ウォーターポンプ
- 透明チューブ
- バイブレーションモーター


## 体験の流れ
1. 操作方法の説明
    - 体験者に基本的な操作方法を解説。
2. 装置の装着
    - 体験者は水冷スーツやリュック型タンク、HMD、ヘッドホンを装着
3. ゲーム開始
    - タイトル画面表示、ストーリー表示
4. ゲーム中
    - その場で足踏みをすることで移動
    - 時間経過で疲労度上昇
    - いくつかのミッションをこなす
5. ゲーム終了
    - 疲労度MAXでゲームオーバー
    - ゴール地点につくとゲームクリア
6. 終了
    - すべての装置を取り外してもらう。

## 制作スケジュール
ソフトウェア  
6月上旬・・・詳細決定、設計  
6月下旬・・・開発開始、VRシステム構築、ステージ作成  
7月上旬・・・移動、疲労度、アイテム等の基礎部分実装  
7月下旬・・・VRのみでゲームプレイができる状態まで  
8月上旬・・・演出強化、ハード部分との連動  
8月下旬・・・デバッグ、ブラッシュアップ  
9月上旬・・・最終準備  

ハードウェア  
6月上旬・・・技術検証  
6月下旬・・・開発開始、デバイス購入、システム設計  
7月上旬・・・制御システム、疲労度タンク、低体温症スーツ、手足バイブレーション  
7月下旬・・・疲労度タンク、低体温症スーツ、手足バイブレーション  
8月上旬・・・ソフト側からの制御  
8月下旬・・・ソフト部分と結合、デバッグ、ブラッシュアップ  
9月上旬・・・最終準備  

## 参考文献
- [令和2年における山岳遭難の概況](https://www.npa.go.jp/publications/statistics/safetylife/chiiki/R02sangakusounan_gaikyou.pdf)

- [触覚ディスプレイ](https://kaji-lab.jp/ja/index.php?plugin=attach&refer=people%2Fkaji%2Fpublications&openfile=tactile.pdf)


### 低体温症
https://sangakujro.com/%E6%95%91%E6%80%A5%E6%B3%95%EF%BC%9A%E4%BD%8E%E4%BD%93%E6%B8%A9%E7%97%87/

https://yamahack.com/2743

https://www.jbpo.or.jp/crossheart/maintenance/14/

### 冷却ベスト
https://www.monotaro.com/k/store/%E6%B0%B4%E5%86%B7%E5%86%B7%E5%8D%B4%E3%82%AF%E3%83%BC%E3%83%AB%E3%83%99%E3%82%B9%E3%83%88/

---

イメージ写真撮影に必要なもの
- 疲労演出
    - チューブ
    - ペットボトル
    - リュック
- 低体温症演出
    - チューブ
- 振動手首
    - とくになし
- 斜面（地面）
    - とくになし
---


## 企画書フォーマット
### 企画書の書式について

提出時は必ずPDFに変換してください。  
　用紙サイズはA4、ページ数は9ページ以内です。1ページ目は表紙です。  
- １ページ目・・・・・表紙  
（作品名を記載。チーム名は記載しないこと）
- ２～９ページ目・・・本文  
メインのフォントは10ポイントとなるようにして書いてください。  
また、上下左右には、おおよそ以下の余白を設けてください。  
上30mm、下25mm、左25mm、右25mm
　
### 内容について

企画書には、主に以下の内容を含めてください。
* 企画名
* 企画の目的とするもの
* システム構成、使用機材
* 制作物の概要と完成予想図
* 制作スケジュール
* その他必要と思われる項目

なお、ページ数と最低限の書式さえ守られていれば、企画書の内容は比較的自由です。自らの企画を審査員に最大限アピールできるような企画書を作成してください。

### 注意点

　IVRC応募書類のオンライン審査はダブルブラインド制（審査する人が応募者の出自・所属を知らない状態での審査）で行われます。表紙を含めた企画書内で、出自が分かる情報を載せないようにしてください。これには参加チーム名、所属団体名、氏名、メールアドレス、チームメンバーの顔写真などが該当します。
