---
lab:
    title: 'ラボ 3: キャンバス アプリを作成する'
    module: 'モジュール 3: Power Apps でキャンバス アプリをカスタマイズする'
---

# 演習 3 – キャンバス アプリを作成する

このラボでは、キャンバス アプリをゼロから設計して構築し、データ ソースとギャラリーを追加します。

## 学習する内容

- データ ソースにリンクされたギャラリーを含むキャンバス アプリを作成する方法
- Power Fx 数式を使用してフィールドを書式設定する方法

## ハイレベルラボの手順

- キャンバス アプリをブランクから作成する
- データソースをアプリに追加する
- アプリにギャラリーを追加する
- ギャラリーのフィールドを構成する
  
## 前提条件

- **ラボ 2: データモデル** を完了している必要があります。

## 詳細な手順

## 演習 1 – キャンバス アプリを作成する

### タスク 1.1 - アプリを作成する

1. Power Apps メーカー ポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認してください。

1. 左側のメニューから **+ Create** タブを選択します。

1. **Start from** の下にある **Blank app** タイルを選択します。

    ![Screenshot of create from blank.](../media/create-from-blank.png)

1. **Blank canvas app** タイルの下にある **Create** を選択します。

1.  **App name** に、 `Booking Request app` と入力します。

1.  **Format** で **Tablet** を選択します。

    ![Screenshot of new app name.](../media/app-name-format.png)

1. **Create** を選択します。

1. アプリが構築されるまで待ちます。

1. Power Apps Studio の右上にある **Save** を選択します。

### タスク 1.2 - データ ソースの追加

1. アプリの作成メニューで、 **Data** を選択します。

    ![Screenshot of Data pane.](../media/studio-data-pane.png)

1. **Add data** の横にあるドロップダウンキャレットを選択し、 **Search** に 'Booking' と入力します。

    ![Screenshot of select data source.](../media/studio-data-search.png)

1. **Booking Requests** Microsoft Dataverse テーブルを選択します。

### タスク 1.3 - メイン画面の構成

1. アプリの作成メニューで、 **Tree view** を選択します。

1. ツリービューで、 **Screen1** を選択し、省略記号(**...**) を選択し、 **Rename** を選択します。

1. `MainScreen` を選択します。

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Rectangle** を選択します。

1. 四角形を画面の左上にドラッグします。

1. アプリの作成メニューで、 **Tree view** を選択します。

1. 四角形の名前を `HeaderRect` に変更します。

1. 長方形のプロパティを次のように設定します:

   1. X=`0`
   1. Y=`0`
   1. Height=`80`
   1. Width=`Parent.Width`

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Text label** を選択します。

1. ラベルを画面の左上にドラッグします。

1. アプリの作成メニューで、 **Tree view** を選択します。

1. ラベルの名前を、 `HeaderLabel` に変更します。

1. ラベルのプロパティを次のように設定します:

   1. X=`0`
   1. Y=`0`
   1. Height=`80`
   1. Width=`Parent.Width`
   1. Align=`Align.Center`
   1. Size=`24`
   1. Text=`"Booking Request"`
   1. Color=`Color.White`

    ![Screenshot of the main screen with header.](../media/main-screen.png)

1. Power Apps Studio の右上にある、 **Save** を選択します。

### タスク 1.4 - ギャラリーを追加する

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Vertical gallery** を選択します。

    ![Screenshot of adding a gallery.](../media/add-gallery.png)

1. **Booking Requests** を選択します。

    ![Screenshot of gallery properties.](../media/gallery-properties.png)

1. **Layout** で、 **Title, subtitle, and body** を選択します。

1. **Fields** の横にある **7 selected** を選択します。

1. **Body** に **Cost** を選択します。

1. **Subtitle** で **Decision** を選択します。

1. **Title** として、 **Pet Name** を選択します。

    ![Screenshot of gallery fields.](../media/select-fields.png)

1. データペインを閉じます。

1. アプリの作成メニューで、 **Tree view** を選択します。

1. ギャラリーの名前を `BookingRequestList` に変更します。

1. ギャラリーのプロパティを次のように設定します:

   1. X=`0`
   1. Y=`80`
   1. Height=`575`
   1. Width=`250`

### タスク 1.5 - 通貨フィールドのフォーマットを設定する

1. アプリの作成メニューで、 **Tree view** を選択します。

1. ギャラリーを展開します。

1. body を選択します。

    ![Screenshot of body field selected.](../media/body.png)

1. **Text** プロパティを次の数式に設定します:

    ```powerappsfl
    Text(Value(ThisItem.Cost), "$#,##0.00")
    ```

1. Power Apps Studio の右上にある **Save** を選択します。

1. コマンドバーの左上にある **<- Back** ボタンを選択し、 **Leave** を選択し、アプリを終了します。
