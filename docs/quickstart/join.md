---
title: クイック スタート - Visual Studio Live Share を参加させる |Microsoft Docs
description: 最初、Visual Studio Live Share コラボレーション セッションに参加することで簡略のチュートリアルです。
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: d4280484aaa3fd4ac204588bf4aefc4e3ac51871
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256067"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-join-your-first-collaboration-session"></a>クイック スタート: 最初の共同作業セッションに参加します。

> **注:現在、Visual Studio Live Share はプレビュー段階です。ユーザー エクスペリエンスと機能は最終版ではありません。**

Visual Studio Live Share へようこそ。 Live Share を使うと、使っているプログラミング言語や構築しているアプリの種類に関係なく、リアルタイムで他のユーザーと共同で編集したりデバッグしたりできます。 これを使用すると、チームメイトの現在のプロジェクトをすぐにかつ安全に参加し、必要に応じて、デバッグ セッションを入力し、表示し編集ターミナル インスタンス、localhost の web アプリや結合の音声通話を参照してください。

開始する準備はできましたか。 チームの共同作業する必要がありますのでクイック自然でしない困難になります。 このため、Visual Studio Live Share 簡単に開始するには、職場とアイデアを共有にシームレスに開始できるようにします。

> [!TIP]
> "*独自のコラボレーション セッションに参加*" できることをご存知でしたか。 これを使うと、Live Share を独自に試したり、Visual Studio または VS Code のインスタンスを起動してリモートでそれに接続したりできます。 両方のインスタンスで同じ ID を使用することもできます。 ぜひお試しください。

コラボレーション セッションに参加する次の手順に従ってください。

## <a name="1-install-the-extension"></a>1.拡張機能をインストールします。

拡張機能をインストールすることは簡単です。 次の手順。

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0+)</strong><br />
        1. Windows (7、8.1、または 10)、macOS <b>(Sierra+)</b>、64 ビット Linux <b>(<a href="../use/vscode.md#installation">詳細</a>)</b> 用の <a href="https://code.visualstudio.com/">Visual Studio Code</a> をインストールします<br />
        2. マーケットプレースから Visual Studio Live Share 拡張機能をダウンロードしてインストールします。 <br />
        3. 再度読み込み、依存関係がダウンロードおよびインストールされるまで待機します (ステータス バーを参照)。<br />
        4. <strong>Linux</strong>:<a href="../reference/linux.md#install-linux-prerequisites">ライブラリのインストール</a>を求められた場合は、インストールをクリックし、パスワードを入力して、完了したら VS Code を再起動します。<br />
        <a href="https://aka.ms/vsls-dl/vscode" alt="Download button"><img src="../media/download.png"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide.svg" width="128px" alt="Visual Studio logo" /></td>
    <td style="border:none;">
        <strong>Visual Studio 2017 15.6 以上</strong><br />
        1. 最新バージョンの <a href="https://visualstudio.microsoft.com/vs/">Visual Studio 2017</a> (15.6+) を Windows (7、8.1、または 10) にインストールします。<br/>
        2. <a href="../reference/platform-support.md">サポートされているワークロード</a>をインストールします。 (例: ASP.NET、.NET Core、C++、Node.js)<br />
        3. マーケットプレースから Visual Studio Live Share 拡張機能をダウンロードしてインストールします。 <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button"></a><br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-preview.svg" width="128px" alt="Visual Studio Preview logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. 最新のプレビュー バージョンの <a href="https://aka.ms/vs-preview">Visual Studio 2019</a> をインストールします。<br/>
        2. <a href="../reference/platform-support.md">サポートされているワークロード</a>をインストールします。 (例: ASP.NET、.NET Core、C++、Node.js)<br />
        3. Visual Studio Live Share は、既定でこれらのワークロードと共にインストールされます。 <br />
    </td>
</tr>
</table>

Visual Studio Live Share をダウンロードして使用すると、[ライセンス条項](https://aka.ms/vsls-license)と[プライバシーに関する声明](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)に同意したものと見なされます。 問題が発生した場合は、[トラブルシューティング](../troubleshooting.md)に関するページをご覧ください。

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2。 (VS Code での読み取り専用ゲストとして省略可能) の結合

Live Share の拡張機能をインストール、再起動、および依存関係の待機後の VS Code で、インストールを完了するにジャンプし、読み取り専用のゲストとして共同作業セッションに参加できます。

> [!NOTE]
> 必要がありますを追加するコードを編集する場合は、[サインイン](../quickstart/join.md#3-Sign-in)します。

ブラウザーで、招待のリンクを開く (または再び開く) と、ブラウザーが VS Code を起動することの通知が表示されます。 起動すると、それを使用して、コラボレーション セッションへの接続が開始します。

VS Code を起動すると、サインインするよう求めるトースト通知が届きます。 [読み取り専用のゲストとして続行] を選択します。 セッションに参加します。

![読み取り専用のゲスト トーストとしてセッションに参加します。](../media/vscode-read-only-guest.png)

参加者はセッション内で識別する表示名を入力を求め。

![読み取り専用のゲスト名](../media/vscode-read-only-guest-name.png)

その後、する読み取り専用としてセッションに参加します。 表示され、コード、共同のデバッグおよび表示の共有サーバー (読み取り専用) の端末内を移動することができます。

> [!NOTE]
> 後で、コードへの読み取り/書き込みアクセスを取得する場合にサインインすることができます。 状態、バー、およびオプション"Sign in"を選択、表示名をクリックします。
![読み取り専用のゲスト サインイン](../media/vscode-read-only-guest-signin.png)これにより、ブラウザーが起動し、Microsoft アカウントまたは GitHub アカウントでサインインすることができます。

## <a name="3-sign-in"></a>3.サインイン

Live Share の拡張機能をインストール、再起動、および依存関係 (VS Code) のインストールを完了するを待つ後、は、2 人の他の参加者にサインインします。 この手順をスキップする場合、参加プロセス中にサインインするように求められますか、読み取り専用のゲストとしてセッションに参加できます。 「共有」のステータス バー項目 (VS Code) をクリックします、サインイン ボタンを開始するには、(VS)。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

**VS Code**、お使いのブラウザーが、通知が表示されますサインインを求める起動中に起動されます。 プロセス ブラウザーでサインインを完了し、実行時にブラウザーを閉じるだけです。

![Web ブラウザーを使用してサインインするよう求めるトースト通知](../media/vscode-sign-in-toast.png)

> **Linux ユーザー:** 以前のバージョンの Live Share を使用している場合は、ユーザー コードを入力を求め可能性があります (v0.3.295 以下)。 拡張機能の最新バージョンに更新するか、「問題ですか?」をクリックします。 コードを参照してください。 サインイン後にリンクします。 参照してください[詳細についてはここで](../use/vscode.md#sign-in-using-a-user-code)します。

**Visual Studio**、Live Share を自動的に使用して、[パーソナル化アカウント](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)します。 その結果、できますサインインするだけ、通常どおりです。 ただしにより、Visual Studio のパーソナル化アカウントも別のサインインを使用する場合は、移行**ツール&gt;オプション&gt;Live Share&gt;ユーザー アカウント**別の資格情報を選択します。

参照してください[トラブルシューティング](../troubleshooting.md#sign-in)も問題に達した場合は。

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4.開く/再-open ブラウザーで、招待のリンク

ここで、開くだけで (または再び開く)、ブラウザーでの招待のリンク。

> **注**:Live Share の拡張機能をインストールしていない場合、拡張機能マーケットプ レースへのリンクが表示されます。 拡張機能のインストールし再起動、ツール、再試行してください。

ブラウザーが Live Share を有効になっているツールを起動する必要があることに通知する必要があります。 選択したツールを起動する場合は、起動した場合は、共同作業セッションに接続できます。

![ページを参加します。](../media/join-page.png)

ホストがオフラインの場合は、通知されますこの時点で代わりにします。 ホストに接続し、もう一度共有するように依頼できます。

> **トラブルシューティングのヒント。** VS Code を使用する場合は、したことを確認する**ツールを少なくとも 1 回開始**した後、拡張機能をインストールして、依存関係のインストールが完了を待機した (ステータス バーを参照してください) する前に開始/再-opening 招待ページ。 問題が解決しますか。 参照してください[を手動で結合](../reference/manual-join.md)詳細についてはします。

## <a name="5-collaborate"></a>5.共同作業を行います。

これで完了です。 数分後には、同僚の共同作業セッションに接続するします。 既定では、ホスト自動-を受け入れる場合、ホストするように設定が、参加する人[ゲストの承認を要求する](../reference/security.md#requiring-guest-approval)は、ステータス バーが表示/への参加要求を承認するホストを待機している Live Share ダイアログ メンションを結合します。

> **セキュリティのヒント:** コラボレーション セッションに参加する、ゲストとしては、ホストが特定のファイルや機能にアクセスを制限することがあることを理解しておく必要です。 Live Share の機能と設定の一部のセキュリティの影響について理解をしますか。 チェック アウト、[セキュリティ](../reference/security.md)記事。

いくつかの操作を試してみてを次に示します。

1. プロジェクトを個別に移動し、いくつかの編集を行う
2. JavaScript、TypeScript、用にチェック アウト作業 intellisense やC#コード
3. ホストと共にオブジェクトを編集します。
4. 次のホストと移動し、別のファイルの編集を行うに移動
5. ホストと同じデバッグ セッションを開始します。
6. 自分のマシンで実行されている web アプリのようなものをチェックできるようにサーバーを共有するホストを確認します。
7. ターミナルを共有し、いくつかのコマンドを実行するホストを確認します。

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。

## <a name="next-steps"></a>次の手順

詳細についてはこれらの記事を確認します。

- [クイック スタート:最初のプロジェクトを共有します。](share.md)
- [方法:Visual Studio Code を使用して共同作業します。](../use/vscode.md)
- [方法:Visual Studio を使用して共同作業します。](../use/vs.md)

参照

- [Live Share の接続要件](../reference/connectivity.md)
- [Live Share のセキュリティ機能](../reference/security.md)
- [言語とプラットフォームのサポート](../reference/platform-support.md)
- [拡張機能のサポート](../reference/extensions.md)
