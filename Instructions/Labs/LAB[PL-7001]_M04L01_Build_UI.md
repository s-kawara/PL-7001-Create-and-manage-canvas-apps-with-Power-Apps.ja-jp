---
lab:
    title: 'ラボ 4: UI を構築する'
    module: 'モジュール 4: Power Apps のキャンバス アプリで UI を構築する方法'
---

# 演習 4 – UI を構築する

このラボでは、アプリ内のコントロールの色を変更します。

## 学習する内容

- テーマの使用方法
- アプリをパーソナライズする方法

## ハイレベルラボの手順

- テーマの選択
- パーソナライゼーション
  
## 前提条件

- **ラボ 3: キャンバスアプリを作成する** を完了している必要があります。

## 詳細な手順

## 演習 1 – テーマ

### タスク 1.1 - アプリを編集する

1. Power Apps メーカー ポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側メニューから **Apps** タブを選択します。

1. **Booking Request app** を選択し、コマンド(**...**) を選択し、 **Edit > Edit in new tab** を選択します。

### タスク 1.2 - テーマの選択

1. Power Apps Studio のアクションバーで、 **Theme** を選択します。

    ![Screenshot of select themes.](../media/select-theme.png)

1. **Red** テーマを選択します。

### タスク 1.3 - ブランド管理

1. アプリの作成メニューで、 **Tree view** を選択します。

1. ギャラリーを展開します。

1. **NextArrow** を選択します。

1. NextArrow の **Color** プロパティを次のように設定します:

    ```powerappsfl
    RGBA(164, 38, 44, 1)
    ```

1. **Body** を選択します。

1. Body の **Color** プロパティを次のように設定します:

    ```powerappsfl
    If(ThisItem.Cost > 1000, RGBA(164, 38, 44, 1), Color.Black)
    ```

1. Power Apps Sutido の右上にある **Save** を選択します。

## 演習 2 – パーソナライゼーション

### タスク 2.1 - ユーザーラベルの追加

1. 空白のキャンバスでギャラリーの外側をクリックします。

1. アプリの選択メニューで、 **Insert (+)** を選択します。

1. **Text label** を選択します。

1. ラベルを画面の右上にドラッグします。

1. アプリの作成メニューで、 **Tree view** を選択します。

1. ラベルの名前を `UserLabel` に変更します。

1. ラベルのプロパティを次のように設定します:

   1. X=`1100`
   1. Y=`20`
   1. Height=`40`
   1. Width=`250`
   1. Align=`Align.Right`
   1. Size=`18`
   1. PaddingRight=`10`
   1. Color=`Color.White`
   1. Text=`User().FullName`

    ![Screenshot of the main screen with personalization.](../media/main-screen-personalized.png)

1. Power Apps Studio の右上にある **Save** を選択します。

1. コマンドバーの左上にある **<- Back** ボタンを選択し、 **Leave** を選択し、アプリを終了します。
