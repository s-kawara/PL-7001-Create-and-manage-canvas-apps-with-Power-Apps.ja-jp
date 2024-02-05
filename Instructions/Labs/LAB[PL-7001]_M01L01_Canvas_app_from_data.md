---
lab:
    title: 'ラボ 1: データからキャンバス アプリを作成する'
    module: 'モジュール 1: Power Apps キャンバス アプリの使用を開始する'
---

# 演習 1 – データからキャンバス アプリを作成する

このラボでは、既存のデータ ソースからキャンバス アプリを設計および構築します。

## 学習する内容

- CoPilot を使用してデータから Power Apps キャンバス アプリを作成する方法
- OneDrive for Business をデータ ソースとして使用して Excel に接続する方法

## ハイレベルラボの手順

- 3 画面のキャンバス アプリを作成する
- アプリをテストする
- CoPilot を使用してキャンバス アプリを作成する
  
## 前提条件

- **ラボ 0: ラボ演習の検証** を完了している必要があります。

## 詳細な手順

## 演習 1 – データを取得する

### タスク 1.1 - Excel スプレッドシートをダウンロードする

1. [CoffeeMachineData.xlsx](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/power-apps/coffee-machine-data/CoffeeMachineData.xlsx) に移動します。

1. **Raw** ファイルボタンを選択して、Excel ワークブックをダウンロードします。

    ![Screenshot of Raw download icon in GitHub.](../media/raw-download.png)

### タスク 1.2 OneDrive for Business にアップロードする

1. [Power Apps メーカーポータル](https://make.powerapps.com) で、ブラウザーウィンドウの左上にある **App launcher** を選択し、 **OneDrive** を選択します。

    ![Screenshot of OneDrive icon.](../media/select-onedrive.png)

1. **Your OneDrive is ready** を選択します。

1. **+ Add new** を選択し、次に **Files upload** を選択します。

    ![Screenshot of OneDrive file upload.](../media/select-onedrive-upload.png)

1. 'ダウンロード' に移動し、CoffeeMachineData.xlsx ファイルを選択し、 **Open** を選択します。

1. **My files** を選択し、 CoffeeMachineData.xlsx がアップロードされていることを確認します。

## 演習 2 – 3 画面のキャンバス アプリを構築する

### タスク 2.1 - アプリの作成

1. Power Apps メーカーポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側メニューから **+ Create** タブを選択します。

1. **Start from** の下にある **Excel** タイルを選択します。

    ![Screenshot of Start from Excel.](../media/start-from-excel.png)

1. **+ New connection** を選択します。

1. **OneDrive for Business** を選択し、 **Create** を選択し,テナントの資格情報でサインインして、 **Allow access** を選択します。

1. [Excel ファイルの選択]で、 **CoffeeMachineData.xlsx** Excel ファイルを見つけます。

1. [テーブルの選択] で、 **CoffeeMachines** を選択します。

1. **Connect** を選択します。

1. アプリが構築されるまで待ちます。

    ![Screenshot of Browse screen in a three screen app.](../media/three-screen-app-browse-screen.png)

1. Power Apps Studio の右上にある **Save** を選択し、 `Coffee Machines App` と入力し、 **Save** を選択します。

### タスク 2.2 - アプリをテストする

1. Power Apps Studio の右上にある **Preview the app** アイコンを選択します。

1. ギャラリー内の任意のマシンを選択します。 詳細画面に移動します。

1. アプリの右上にある **Edit** アイコンを選択し、編集画面を開きます。

1. **Machine Price** を変更し、アプリの右上にある **Submit** アイコンを選択します。

1. アプリの左上にある **<** アイコンを選択します。

1. アプリの右上にある **+** アイコンを選択します。

1. **Machine ID** に '97' を入力します。

1. **Machine Name** に `Demo Machine` を入力します。

1. **Machine Price** に `999` を入力します。

1. アプリの右上にある **Submit** アイコンを選択します。

1. **Search items** に `Demo` を入力します。

1. プレビューを停止するには、右上隅の **X** を選択します。

1. コマンドバーの左上にある **<- Back** ボタンを選択し、 **Leave** を選択し、アプリを終了します。

1. Power Apps メーカーポータルの左側のメニューから **+ Create** タブを選択します。

## 演習 3 – Copilot を使用してキャンバス アプリを構築する

### Task 3.1 - Create the app

1. Power Apps メーカーポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のメニューから **Home** タブを選択します。

1. **Let's build an app. What should it do?** の下から `Track coffee machine repairs for customers and assign repairs to technicians` を入力し、矢印アイコンを選択します。

    ![Screenshot of copilot prompt.](../media/copilot-prompt.png)

1. テーブルを確認する

    ![Screenshot of copilot table.](../media/copilot-table.png)

1. **Create app** を選択します。

1. アプリが構築されるまで待ちます。

    ![Screenshot of app by by copilot.](../media/copilot-app.png)

1. Power Apps Studio の右上にある **Save** を選択し、`Coffee Repair App` と入力し、 **Save** を選択します。

1. コマンドバーの左上にある **<- Back** ボタンを選択し、 **Leave** を選択しアプリを終了します。

1. Power Apps メーカーポータルの左側のメニューから **Apps** タブを選択します。
