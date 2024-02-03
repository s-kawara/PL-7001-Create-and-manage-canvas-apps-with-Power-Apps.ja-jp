---
lab:
    title: 'ラボ 2: データ モデル'
    module: 'モジュール 2: Microsoft Dataverse の使用を開始する'
---

# 演習 2 – データ モデル

このラボでは、Dataverse のテーブルと列を作成します。

## 学習する内容

- Microsoft Dataverse でテーブルと列を作成する方法
- ルックアップ列との関係を作成する方法

## ハイレベルラボの手順

- カスタムテーブルを作成する
- テーブルに列を追加する
- ルックアップ列を使用して との関係を作成する
  
## 前提条件

- **Lab 0: Validate lab environment** が完了している必要があります。

## 詳細な手順

## 演習 1 – カスタム テーブルを作成する

### タスク 1.1 - 予約リクエストテーブルを作成する

1. Power Apps メーカーポータル <https://make.powerapps.com> に移動します。

1. **Dev One** にいることを確認してください。

1. 左側のナビゲーションウィンドウで **Tables** を選択します。

1. **+ New table** を選択し、 **Add columns and data** を選択します。

    ![Screenshot of creating a new table in Dataverse.](../media/create-new-table-dataverse.png)

1. '新しいテーブル' 横にある **pencil** アイコンを選択します。

    ![Screenshot of new table name.](../media/table-name.png)

1. **Display name** に `Booking Request` と入力します。

1.  **Save** を選択します。

### タスク 1.2 - プライマリ列

1. **New column** の横にあるドロップダウンキャレットを選択し、 **Edit column** を選択します。

    ![Screenshot of primary column.](../media/primary-column.png)

1. **Display name** に `Pet Name` を入力します。

1. **Update** を選択します。

1. **Create** を選択します。

### タスク 1.3 - 列の追加

1. **Booking Request columns and data** ペインで、 **+** を選択し、新しい列を追加します。

    ![Screenshot of data pane.](../media/data-pane.png)

1. **New column** ペインで、次の値を入力または選択します:

   1. 表示名: `Owner Name`
   1. データ型: **Single line of text**
   1. 必須: **Business required**

    ![Screenshot of new column pane.](../media/new-column-pane.png)

1. **Save** を選択します。

1. **Booking Request columns and data** ペインで、 **+** を選択し、新しい列を追加します。

1. **New column** ペインで、次の値を入力または選択します:

   1. 表示名: `Owner Email`
   1. データ型: **Single line of text**
   1. 形式: **Email**
   1. 必須: **Business required**

1. **Save** を選択します。

1. **Booking Request columns and data** ペインで、 **+** を選択し、 **New column** ペインで次の値を入力または選択します:

   1. 表示名: `Start Date`
   1. データ型: **Date and time**
   1. 必須: **Business required**

1. **Save** を選択します。

1. **Booking Request columns and data** ペインで、 **+** を選択し、 **New column** ペインmで次の値を入力または選択します:

   1. 表示名: `End Date`
   1. データ型: **Date and time**
   1. 必須: **Optional**

1. **Save** を選択します。

1. **Booking Request columns and data** ペインで、 **+** を選択し、 **New column** ペインで次の値を入力または選択します:

   1. 表示名: `Cost`
   1. データ型: **Currency**
   1. 必須: **Optional**

1. **Save** を選択します。

1. **Booking Request columns and data** ペインで、 **+** を選択し、 **New column** ペインで次の値を入力または選択します:

   1. 表示名: `Notes`
   1. データ型: **Multiple lines of text**
   1. フォーマット: **Text**
   1. 必須: **Optional**

### タスク 1.4 - 選択列の追加

1. **Booking Request columns and data** ペインで、 **+** を選択し、 **New column** ペインで次の値を入力または選択します:

   1. 表示名: `Decision`
   1. データ型: **Choice**
   1. 必須: **Optional**

1. **Sync with global choice?** で、 **No** を選択します。

1. **Label** に、 `Undecided` と入力し、 **Value** に、 `1` を入力します。

1. **+ New choice** を選択し、**Label** に、 `Accepted` を入力し、**Value** に、 `2` を入力します。

1. **+ New choice** を選択し、 **Label** に、 `Declined` と入力し、 **Value** に `3` を入力します。

1. **Default choice** として、 **Undecided** を選択します。

    ![Screenshot of new choice column pane.](../media/new-local-choice.png)

1. **Save** を選択します。

## 演習 2 – リレーションシップを作成する

### タスク 2.1 - ルックアップ列の作成

1. Power Apps メーカー ポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のナビゲーションウィンドウで、 **Tables** を選択します。

1. **Booking Request columns and data** ペインで、 **+** を選択し、 **New column** ペインで次の値を入力または選択します:

   1. 表示名: `Account`
   1. データ型: **Lookup**
   1. 必須: **Optional**
   1. リレーションテーブル: **Account**

    ![Screenshot of new lookup column pane.](../media/new-lookup.png)

1. **Save** を選択します。
