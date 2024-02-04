---
lab:
    title: 'ラボ 6: フォーム'
    module: 'モジュール 6: Power Apps キャンバス アプリにデータを書き込む'
---

# 演習 6 – フォーム

このラボでは、フォームを使用してデータ ソース内のレコードを作成および編集します。

## 学習する内容

- 画面の追加方法
- 画面間を移動する方法
- フォームを使用してデータ ソースにレコードを作成する方法
- フォームを使用してデータ ソース内のレコードを編集する方法
- データソースからレコードを削除する方法
- フォームをギャラリーにリンクする方法

## ハイレベルラボの手順

- 新しい画面を作成する
- ギャラリーでレコードが選択されているときの画面に移動します
- 画面間を移動する
- フォームでレコードを表示する
- レコードを削除する
- フォームを使用してレコードを編集する
- フォームで新しいレコードを作成する
  
## 前提条件

- **ラボ 5: 外部データ** を完了している必要があります。

## 詳細な手順

## 演習 1 – 画面とナビゲーションを追加する

### タスク 1.1 - アプリを編集する

1. Power Apps メーカー ポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側メニューから **Apps** タブを選択します。

1. **Booking Request app** を選択し、コマンド (**...**) を選択し、 **Edit > Edit in new tab** を選択します。

### タスク 1.2 - 画面の追加

1. アプリの作成メニューで、 **Tree view** を選択します。

1. Power Apps Studio のアクションバーで、 **New screen** を選択します。

    ![Screenshot of new screen.](../media/add-screen.png)

1. **Blank** を選択します。

1. 画面の名前を `EditScreen` に変更します。

1. Power Apps Studio のアクションバーで、 **New screen** を選択します。

1. **Header and footer** を選択します。

1. 画面の名前を `DetailScreen` に変更します。

### タスク 1.3 - ナビゲーションの追加

1. **MainScreen** 画面の  **BookingRequestList** で、 **NextArrow** を選択します。

1. NextArrow の **OnSelect** プロパティを次のように設定します:

    ```powerappsfl
    Collect(colRequests, ThisItem);Navigate(DetailScreen, ScreenTransition.Cover);
    ```

1. **EditScreen** を選択します。

1. アプリの作成メニューで、**Insert (+)** を選択します。

1. **Icons** を展開します。

1. **Back arrow** を選択します。

1. icon の **OnSelect** プロパティを次のように設定します:

    ```powerappsfl
    Back()
    ```

1. **Tree view** で、アイコンを選択し、コマンド (**...**) を選択し、 **Copy** を選択します。

1. **DetailScreen** を展開します。

1. **HeaderContainer** を選択し、コマンド (**...**) を選択し、 **Paste** を選択します。

## 演習 2 – 詳細画面

### タスク 2.1 - 表示フォームの追加

1. アプリの作成メニューで、 **Tree view** を選択します。

1. **DetailScreen** を展開します。

1. **ScreenContainer** を展開します。

1. **MainContainer** を選択します。

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Input** を展開します。

1. **Display form** を選択します。

    ![Screenshot of adding a display form.](../media/add-display-form.png)

1. FormViewer プロパティで、  **Data source** に **Booking Requests** を選択します。

1. **Fields** 横にある **2 selected** を選択します。

    ![Screenshot of default form fields.](../media/add-fields-default.png)

1. field の横にある省略記号  (**...**) を選択し、 **Remove** を選択し、 **Created On** を削除します。

1. **+ Add field** を選択し、次のフィールドを選択します:

   1. Cost
   1. Decision
   1. End Date
   1. Owner Email
   1. Owner Name
   1. Start Date

    ![Screenshot of adding fields to the form.](../media/add-fields.png)

1. **Add** を追加します。

1. フィールドを次の順序でドラッグします:

   1. Pet Name
   1. Owner Name
   1. Owner Email
   1. Start Date
   1. End Date
   1. Decision
   1. Cost

    ![Screenshot of sorting the form fields.](../media/add-fields-sorted.png)

1. **Fields** ペインで **Close** を選択します。

1. form viewer コントロールの **Item** プロパティを次のように設定します:

    ```powerappsfl
    BookingRequestList.Selected
    ```

### タスク 2.2 - ラベルの追加

1. アプリの作成メニューで、 **Tree view** を選択します。

1. **DetailScreen** を展開します。

1. **ScreenContainer** を展開します。

1. **FooterContainer** を選択します。

1. Footer コンテイナー内で、 **+** を選択します。

    ![Screenshot of adding a control to the container.](../media/add-control-container.png)

1. **Text label** を選択します。

1. ラベルの **Text** プロパティを次のように設定します:

    ```powerappsfl
    BookingRequestList.Selected.'Pet Name'
    ```

### タスク 2.3 - 削除ボタンの追加

1. アプリの作成メニューで、 **Tree view** を選択します。

1. **DetailScreen** を展開します。

1. **ScreenContainer** を展開します。

1. **FooterContainer** を選択します。

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Button** を選択します。

1. アプリの作成メニューで、 **Tree view** を選択します。

1. Button の名前を `Deletebtn` に変更します。

1. Button の **Text** プロパティを次のように設定します:

    ```powerappsfl
    "Delete"
    ```

1. Button の **OnSelect** プロパティを次のように設定します:

    ```powerappsfl
    Remove('Booking Requests', BookingRequestList.Selected); Back();
    ```

## 演習 3 – 編集画面

### タスク 3.1 - 編集フォームの追加

1. アプリの作成メニューで、 **Tree view** を選択します。

1. **EditScreen** を選択します。

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Edit form** を選択します。

1. Form のプロパティで、 **Data source** に **Booking Requests** を選択します。

1. **Fields** の横にある **2 selected** を選択します。

1. field の横にある省略記号 (**...**) を選択し、 **Remove** を選択し、 **Created On** を削除します。

1. **+ Add field** を選択し、次のフィールドを選択します:

   1. Cost
   1. End Date
   1. Owner Email
   1. Owner Name
   1. Start Date

1. **Add** を選択します。

1. フィールドを次の順序でドラッグします:

   1. Pet Name
   1. Owner Name
   1. Owner Email
   1. Start Date
   1. End Date
   1. Cost

1.  **Fields** ペインを **Close** します。

1. フォームコントロールの **Item** プロパティを次のように設定します:

    ```powerappsfl
    BookingRequestList.Selected
    ```

1. アプリの作成メニューで、 **Tree view** を選択します。

1. フォームの名前を `BookingRequestForm` に変更します。

1. フォームのプロパティを次のように設定します:

   1. X=`0`
   1. Y=`125`
   1. Height=`500`
   1. Width=`Parent.Width`
   1. Columns=`1`
   1. Layout=`Horizontal`

    ![Screenshot of the configured booking request form.](../media/bookingrequestform.png)

### タスク 3.2 - 送信ボタンの追加

1. アプリの作成メニューで、 **Tree view** を選択します。

1. **EditScreen** を選択します。

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Button** を選択します。

1. ボタンをフォームの下にドラッグします。

1. アプリの作成メニューで、 **Tree view** を選択します。

1. ボタンの名前を `Submitbtn` に変更します。

1. ボタンの **Text** プロパティを次のように設定します:

    ```powerappsfl
    "Submit"
    ```

1. ボタンの **OnSelect** プロパティを次のように設定します:

    ```powerappsfl
    SubmitForm(BookingRequestForm)
    ```

1. **BookingRequestForm** を選択します。

1. ボタンの **OnSuccess** プロパティを次のように設定します:

    ```powerappsfl
    Navigate(MainScreen, ScreenTransition.UnCover)
    ```

### タスク 3.3 - 編集画面にナビゲーションを追加する

1. アプリの作成メニューで、 **Tree view** を選択します。

1. **DetailScreen** を展開します。

1. **ScreenContainer** を展開します。

1. **HeaderContainer** を選択します。

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Icons** を展開します。

1. **Edit** を選択します。

1. アプリの作成メニューで、 **Tree view** を選択します。

1. アイコンの名前を `EditIcon` に変更します。

1. アイコンの **OnSelect** プロパティを次のように設定します:

    ```powerappsfl
    Navigate(EditScreen, ScreenTransition.Cover)
    ```

### タスク 3.4 - 新しいレコード

1. アプリの作成メニューで、 **Tree view** を選択します。

1. **MainScreen** を選択します。

1. アプリの作成メニューで、 **Insert (+)** を選択します。

1. **Icons** を展開します。

1. **Add** を選択します。

1. アプリの作成メニューで、 **Tree view** を選択します。

1. アイコンの名前を `NewIcon` に変更します。

1. アイコンのプロパティを次のように設定します:

   1. X=`0`
   1. Y=`0`
   1. Height=`80`
   1. Width=`80`
   1. Color=`Color.White`

1. アイコンの **OnSelect** プロパティを次のように設定します:

    ```powerappsfl
    NewForm(BookingRequestForm);Navigate(EditScreen, ScreenTransition.Cover)
    ```

1. Power Apps Studio の右上にある **Save** を選択します。

1. コマンドバーの左上にある **<- Back** ボタンを選択し、 **Leave** アプリを終了します。
