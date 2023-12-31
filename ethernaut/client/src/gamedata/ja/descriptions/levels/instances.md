このレベルでは、ゲームをプレイするための基本的な方法を説明します。

#### 1. Set up MetaMask

If you don't have it already, install the [MetaMask browser extension](https://metamask.io/) (in Chrome, Firefox, Brave or Opera on your desktop machine).
Set up the extension's wallet and use the network selector to point to the preferred network in the top left of the extension's interface. Alternatively you can use the UI button to switch between networks. If you select an unsupported network, the game will notify you and bring you to the default Sepolia testnet.

#### 2. ブラウザのコンソールを開く

ブラウザのコンソールを開きます。`tools > Developer tool`を選択します。

ゲームからのメッセージがいくつか表示されるはずです。そのうちのひとつに、プレイヤーのアドレスが書かれています。これはゲーム中に重要な意味を持ちます。自分のプレイヤーのアドレスは、次のコマンドを入力することでいつでも見ることができます。

```
player
```

ゲーム中に重要な情報が得られる可能性があるので、警告やエラーに注意してください。

#### 3. コンソールヘルパーを使う

また、以下のように入力すると、現在の ether の所有量を確認することができます。

```
getBalance(player)
```

###### 注意: 「pending」と表示されていて、実際の値を確認したい場合は promise を展開してください。Chrome v62 を使用している場合は、`await getBalance(player)` を使用すると、コンソールがすっきりします。

素晴らしいですね。コンソールにある他のユーティリティー関数を見るには、次のように入力します。

```
help()
```

これらは、ゲームプレイ中に超便利です。

#### 4. ethernaut のコントラクト

コンソールで以下のコマンドを入力します。

```
ethernaut
```

これはこのゲームのメインのスマートコントラクトです。コンソールから直接操作する必要はありませんが（このアプリがやってくれるので）、やりたければできます。今、このオブジェクトを使って遊ぶことは、ゲームの他のスマートコントラクトとのやりとりを学ぶのに最適な方法です。

ethernaut オブジェクトを展開して、中身を見てみましょう。

#### 5. ABI とのインタラクト

`ethernaut` は、ブロックチェーンにデプロイされたコントラクト `Ethernaut.sol` をラップした `TruffleContract` オブジェクトです。

とりわけ、コントラクトの ABI は、`Ethernaut.sol`のすべてのパブリックメソッド（`owner`など）を公開しています。例えば以下のようなコマンドを入力します。

```
ethernaut.owner()
```

###### Chrome v62 を使用している場合は、`await ethernaut.owner()`と入力してください。

ethernaut コントラクトの owner が誰であるかを見ることができます。

#### 6. テスト用 ether の入手

To play the game, you will need test ether. The easiest way to get some testnet ether is via a valid faucet for your chosen network.

Once you see some coins in your balance, move on to the next step.

#### 7. レベルインスタンスの取得

レベルをプレイする際には、ethernaut コントラクトと直接対話することはありません。代わりに、**レベルインスタンス**の生成をします。そのためには、ページの下にある青いボタンをクリックします。今すぐ実行して、戻ってきてください。

MetaMask からトランザクションを承認するよう促されるはずです。そうすると、コンソールにいくつかのメッセージが表示されるはずです。これはブロックチェーンに新しいコントラクトをデプロイするもので、数秒かかることがありますので、新しいレベルのインスタンスをリクエストする際には気長にお待ちください

#### 8. コントラクトの検査

ethernaut コントラクトで行ったように、`contract`変数を使ってコンソールからこのコントラクトの ABI を調べることができます。

#### 9. コントラクトとインタラクトしてレベルをクリアする

レベルの情報を見てみましょう。

```
contract.info()
```

###### Chrome v62 を使用している場合は、`await contract.info()` を実行してください。

レベルをクリアするのに必要なものはすべてコントラクトの中にあります。
レベルが完了したら、ページの下にあるオレンジ色のボタンを使ってコントラクトを送信します。
これにより、インスタンスが ethernaut に戻され、完了したかどうかが判断されます。

##### ヒント: コントラクトの ABI はいつでも見ることができます!
