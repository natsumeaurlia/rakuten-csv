# **楽天カード利用明細通知**

このプロジェクトは、楽天カードの利用明細をダウンロードし、支払い金額を計算して LINE Notify を使用して通知するプログラムです。

<img width="310" alt="スクリーンショット 2023-04-13 5 42 08" src="https://user-images.githubusercontent.com/40763821/231580180-b224e8f8-4a82-4c85-8956-38f5c3dac197.png">


## **使い方**

1. プロジェクトをクローンまたはダウンロードします。
2. **`.env.example`** ファイルを **`.env`** にコピーし、必要な環境変数を設定します。
3. **`npm install`** を実行して、依存関係をインストールします。
4. **`npm run start`** を実行して、プログラムを開始します。


## **環境変数**

- **`ID`**: 楽天カードのログイン ID
- **`PASS`**: 楽天カードのログインパスワード
- **`LINE_ACCESS_TOKEN`**: LINE Notify のアクセストークン

## **GitHub Actions**

このプロジェクトには、GitHub Actions を使用して定期的にプログラムを実行するワークフローが含まれています。現在の設定では、毎日 4 時間ごとに実行されます。必要に応じて、スケジュールを変更できます。

## **プログラムの概要**

- **`main.ts`**: Playwright を使用して楽天カードのログインページにアクセスし、利用明細をダウンロードして **`storage`** ディレクトリに保存します。ダウンロードが完了したら、 **`sumTotalPayment`** 関数を呼び出し、合計金額を計算し、LINE Notify を使用して通知します。
- **`util.ts`**: **`sumTotalPayment`** 関数が含まれており、ダウンロードした CSV ファイルを解析して支払い金額を計算します。
- **`line-notify.ts`**: LINE Notify API を使用して通知を送信するための関数が含まれています。

## **注意事項**

このプログラムはあくまでサンプルであり、実際の楽天カードアカウントで使用する際には、適切なセキュリティ対策を講じてください。また、楽天カードのウェブサイトが更新されることがあり、プログラムが正常に動作しなくなる可能性があります。その場合は、適切な修正が必要になります。

また、本プログラムは楽天カード利用明細に関する非公式のものであり、楽天カード株式会社とは一切関係ありません。ご利用にあたっては、自己責任でお願いいたします。

## **ライセンス**

このプロジェクトは MIT ライセンスのもとで公開されています。詳細については、**`LICENSE`** ファイルを参照してください。
