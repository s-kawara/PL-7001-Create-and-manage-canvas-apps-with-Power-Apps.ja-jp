---
lab:
    title: 'ラボ 7: キャンバス アプリを管理する'
    module: 'モジュール 7: キャンバス アプリを公開、共有、および保守する'
---

# 演習 7 – キャンバス アプリの管理

このラボでは、キャンバス アプリを管理します。

## 学習する内容

- キャンバス アプリを共有する方法
- キャンバス アプリのバージョンを管理する方法
- キャンバス アプリを公開する方法
- キャンバス アプリをエクスポートする方法

## ハイレベルラボの手順

- キャンバス アプリを共有する
- キャンバス アプリのバージョンを表示する
- キャンバス アプリを公開する
- キャンバス アプリをエクスポートする
  
## 前提条件

- **ラボ 6: フォーム** を完了している必要があります。

## 詳細な手順

## 演習 1 – 管理

### タスク 1.1 - 予約リクエスト アプリを共有する

1. Power Apps メーカー ポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側メニューから **Apps** タブを選択します。

1. **Booking Request app** を選択し、コマンド (**...**) を選択し、 **Share** を選択します。

    ![Screenshot of share action for an app.](../media/share-app-action.png)

1. 共有ペインで、 `Everyone` と入力し、 **Everyone in Contoso** を選択します。

    ![Screenshot of share app pane.](../media/share-app-pane.png)

1. **Share** を選択します。

1. 共有アプリペインを **Close** します。

### タスク 1.2 - Booking リクエスト アプリを公開する

1. **Booking Request app** を選択し、コマンド (**...**) を選択し、 **Details** を選択します。

1. **Versions** タブを選択します。

    ![Screenshot of app versions.](../media/app-versions.png)

1. 最も上位のバージョンを選択します。

    ![Screenshot of publishing latest version.](../media/app-publish.png)

1. **Publish this version** を選択します。

1. **Publish this version** を再度選択します。

## 演習 2 – エクスポート

### タスク 2.1 - Booking リクエスト アプリをエクスポートする

1. Power Apps メーカー ポータル <https://make.powerapps.com> に移動します。

1. **Dev One** 環境にいることを確認します。

1. 左側のメニューから **Apps** タブを選択します。

1. **Booking Request app** を選択し、コマンド (**...**) を選択し、 **Export package** を選択します。

    ![Screenshot of export app page.](../media/export-package.png)

1. 名前に `Booking Request app` と入力します。

1. **IMPORT SETUP** で、 **Update** を選択します。

1. **Create as new** を選択し、 **Save** を選択します。

1. **Export** を選択します。

1. パッケージが作成されてダウンロードされるまで待ちます。これにより、ダウンロードフォルダーに zip フィルが作成されます。

### タスク 2.2 - アプリをローカルに保存する

1. 左側のメニューから、 **Apps** タブを選択します。

1. **Booking Request app** を選択し、コマンド (**...**) を選択し、 **Edit > Edit in new tab** を選択します。

1. Power Apps Studio の右上にある **Save** の横にあるドロップダウンキャレットを選択します。

1. **Download a copy** を選択します。

1. **Download** を選択します。これにより、ダウンロードフォルダーに msapp ファイルが作成されます。

1. コマンドバーの左上にある **<- Back** ボタンを選択し、 **Leave** を選択してアプリを終了します。
