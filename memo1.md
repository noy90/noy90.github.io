<link rel="stylesheet" href="./style.css">

# wsl が起動しなくなった時の対処

<div style="text-align: right">2022/06/28</div>

ubuntu が起動しない! 結構焦りました。

次起きた時にも対処できるように、メモ書きを残しておきます。

- 環境

  Ubuntu on Windows (Ubuntu 20.04.4 LTS)

- 状況

  ubuntu を起動すると、アンダーラインが点滅するだけ

  powershell で調べてみると wsl コマンドも応答しなくなってた

- 原因

  PC の**仮想化機能**が無効化していた？(した覚えないんですけど…)

- 対処

  1.　 powershell を**管理者権限**で実行し以下を入力

  <textarea name="text" rows="1" wrap="off" spellcheck="false" onfocus="this.select();" readonly>
  dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
  </textarea>

  2.　 PC 自体を再起動する

  これで復旧できました。

<br>

### 参考

> [https://docs.microsoft.com/ja-jp/windows/wsl/troubleshooting](https://docs.microsoft.com/ja-jp/windows/wsl/troubleshooting)
