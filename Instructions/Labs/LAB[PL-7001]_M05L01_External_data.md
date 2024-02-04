---
lab:
    title: 'ラボ 5: 外部データ'
    module: 'モジュール 5: Power Apps キャンバス アプリで外部データを操作する'
---

# 演習 5 – 外部データ

このラボでは、外部データ ソースを追加します。

## 学習する内容

- SharePoint リストをキャンバス アプリに追加する方法
- コレクションの使用方法
- Patch 関数の使い方
- Office365Usersコネクタの使用方法

## ハイレベルラボの手順

- Booking 用の SharePoint リストを作成する
- SharePoint リストをギャラリーとして追加する
- ギャラリーから選択したレコードを保存する
- Patch 関数を使用してBooking リクエストの決定を設定する
- Office365User コネクタを使用してユーザーの詳細を表示する
  
## 前提条件

-  **ラボ 4: UI を構築する** を完了している必要があります。

## 詳細な手順

## 演習 1 – SharePoint リストの作成

### タスク 1.1 SharePoint サイトを作成する

1. [Power Apps maker portal](https://make.powerapps.com) で、ブラウザーの左上にある **App launcher** を選択し、 **OneDrive** を選択します。

1. SharePoint で、 **+Create site** を選択します。

1. **Team site** を選択し、 **Standard team** テンプレートを選択し、 **Use template** を選択します。

1. **Site name** に、 `Pet boarding` と入力し、 **Next** を選択します。

1. **Create site** を選択します。

1. **Finish** を選択します。

### タスク 1.2 SharePoint リストを作成する

1. SharePoint サイトで、 **+ New** を選択し、次に、 **List** を選択します。

    ![Screenshot of new SharePoint list.](../media/new-sharepoint-list.png)

1. **Blank list** を選択します。

1. **Name**  を選択し、 `Bookings` を入力し、 **Create** を選択します。

1. **Add column** 、 **Text**　、 **Next** の順に選択します。

1. **Create a column** ペインで、次の値を入力または設定します:

   1. 名前: `Pet Name`
   1. データ型: **Single line of text**

1. **Save** を選択します。

1. **Add column** 、 **Text** 、 **Next** を順に選択します。

1. **Create a column** ペインで、次の値を入力または選択します:

   1. 名前: `Owner Name`
   1. データ型: **Single line of text**

1. **Save** を選択します。

1. **Add column** 、 **Date and time** 、 **Next** を順に選択します。

1. **Create a column** ペインで、次の値を入力または選択します:

   1. 名前: `Start Date`
   1. データ型: **Date and time**

1. **Save** を選択します。

1. **Add column** 、 **Date and time** 、 **Next** を順に選択します。

1. **Create a column** ペインで、次の値を入力または選択します:

   1. 名前: `End Date`
   1. データ型: **Date and time**

1. **Save** を選択します。

1. SharePoint サイトのURL の最初の部分をコピーします。例: `https://m365x99999999.sharepoint.com/sites/Petboarding/`

## 演習 2 – SharePoint リストをキャンバス アプリに追加する

### タスク 2.1 - アプリを編集する

1. Power Apps メーカー ポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側メニューから **Apps** タブを選択します。

1. **Booking Request app** を選択し、コマンド (**...**) を選択して、 **Edit > Edit in new tab** を選択します。

### タスク 2.2 - SharePoint をデータ ソースとして追加する

1. アプリの作成メニューで **Data** を選択します。

1. **Add data** の横にあるドロップダウンキャレットを選択し、 **Search** に 'SharePoint' と入力します。

    ![Screenshot of select SharePoint as data source.](../media/studio-data-sharepoint.png)

1. **SharePoint** を選択します。

1. **Connect directly (cloud services)** を選択し、 **Connect** を選択します。

1. このラボで前に作成した SharePoint サイトの URL を入力します。

    ![Screenshot of connect to SharePoint site.](../media/select-sharepoint-site.png)

1. **Connect** を選択します。

1. **Bookings** を選択します。

    ![Screenshot of connect to SharePoint list.](../media/select-sharepoint-list.png)

1. **Connect** を選択します。

### タスク 2.3 - SharePoint リストのギャラリーを追加する

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Vertical gallery** を選択します。

1. データソースとして **Bookings** を選択します。

1. **Layout** で **Title and subtitle** を選択します。

1. **Fields** の横にある **6 selected** を選択します。

1. **Title** に **Decision** を選択します。

1. **Subtitle** に **Start Date** を選択します。

1. データ ペインを閉じます。

1. アプリの作成メニューで、 **Tree view** を選択します。

1. ギャラリーの名前を `BookingList` に変更します。

1. ギャラリーのプロパティを次のように設定します:

   1. X=`1000`
   1. Y=`80`
   1. Height=`575`
   1. Width=`250`

## 演習 3 – コレクション

### タスク 3.1 コレクションの作成

1. アプリの作成メニューで、 **Tree view** を選択します。

1. **BookingRequestList** を展開します。

1. **NextArrow** を選択します。

1. **OnSelect** プロパティを次のように設定します:

    ```powerappsfl
    Collect(colRequests, ThisItem)
    ```

1. アプリの作成メニューで、 **Tree view** を選択します。

1. **App** オブジェクトを選択します。

1. **OnStart** プロパティを次のように設定します:

    ```powerappsfl
    Clear(colRequests)
    ```

## 演習 4 – Patch 関数

### タスク 4.1 予約リクエストを拒否する

1. アプリ作成メニューで、 **Tree view** を選択します。

1. **BookingRequestList** を選択します。

1. ギャラリーコントロール左上にある **pencil** アイコンを選択します。

    ![Screenshot of editing the gallery.](../media/edit-gallery.png)

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Icons** を展開します。

1. **Blocked** を選択します。アイコンは、ギャラリーの各行に追加されます。

    ![Screenshot of editing the gallery.](../media/icon-added-gallery.png)

1. アイコンのプロパティを次のように設定します:

   1. X=`150`
   1. Y=`40`
   1. Height=`30`
   1. Width=`30`

1. アプリの作成メニューで、 **Tree view** を選択します。

1. アイコンの名前を `DeclineIcon` に変更します。

1. **DeclineIcon** の **OnSelect** プロパティを次のように設定します:

    ```powerappsfl
    Patch('Booking Requests', ThisItem, {Decision: 'Decision (Booking Requests)'.Declined})
    ```

## 演習 5 – Office 365 ユーザー

### タスク 5.1 Office 365 ユーザーをデータ ソースとして追加する

1. アプリの作成メニューで、 **Data** を選択します。

1. **Add data** の横にあるドロップダウンキャレットを選択し、 **Search** に `Office 365` と入力します。

1. **Office 365 Users** を選択します。

1. **Connect** を選択します。

### タスク 5.2 ユーザーの国を表示する

1. 空白のキャンバスでギャラリーの外側をクリックします。

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Text label** を選択します。

1. ラベルを画面右上の UserLabel の隣にドラッグします。

1. アプリの作成メニューで、 **Tree view** を選択します。

1. ラベルの名前を `UserDetailsLabel` に変更します。

1. **UserDetailsLabel** の **OnSelect** プロパティを次のように設定します:

    ```powerappsfl
    Office365Users.MyProfile().Country
    ```

1. Power Apps Studio の右上にある **Save** を選択します。

1. コマンドバーの左上にある **<- Back** ボタンを選択し、 **Leave** を選択し、アプリを終了します。
