---
title: 参加のクイック スタート - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share コラボレーション セッションに初めて参加するための簡単なチュートリアルです。
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: c1f62cf12797279cc7bcb1a7ee1273667618ab46
ms.sourcegitcommit: cab8df5c29f9d91e702ef514def53944ee7701ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "64987184"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-join-your-first-collaboration-session"></a>クイック スタート: コラボレーション セッションに初めて参加する

Visual Studio Live Share へようこそ。 Live Share を使うと、使っているプログラミング言語や構築しているアプリの種類に関係なく、リアルタイムで他のユーザーと共同で編集したりデバッグしたりできます。 これにより、チームメートの現在のプロジェクトに瞬時に安全に参加した後、必要に応じて、デバッグ セッションへの参加、ターミナル インスタンスの表示および編集、localhost の Web アプリの表示、音声通話への参加などができます。

開始する準備はできましたか。 チーム コラボレーションはすばやく自然に行える必要があり、そうでないとより困難になります。 このため、Visual Studio Live Share はそれを簡単に始められるようにして、仕事とアイデアをシームレスに共有できるようにします。

> [!TIP]
> "*独自のコラボレーション セッションに参加*" できることをご存知でしたか。 これを使うと、Live Share を独自に試したり、Visual Studio または VS Code のインスタンスを起動してリモートでそれに接続したりできます。 両方のインスタンスで同じ ID を使用することもできます。 ぜひお試しください。

コラボレーション セッションに参加するには、次の手順に従います。

## <a name="1-install-the-extension"></a>1.拡張機能をインストールする

拡張機能のインストールは簡単です。 以下の手順を実行します。

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
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1.<a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a> をインストールします。<br/>
        2. <a href="../reference/platform-support.md">サポートされているワークロード</a>をインストールします。 (例: ASP.NET、.NET Core、C++、Python、Node.js)<br />
        3. Visual Studio Live Share は、既定でこれらのワークロードと共にインストールされます。 <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 以上</strong><br />
        1. 最新バージョンの <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a> (15.6+) を Windows (7、8.1、または 10) にインストールします。<br/>
        2. <a href="../reference/platform-support.md">サポートされているワークロード</a>をインストールします。 (例: ASP.NET、.NET Core、C++、Node.js)<br />
        3. マーケットプレースから Visual Studio Live Share 拡張機能をダウンロードしてインストールします。 <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Visual Studio Live Share をダウンロードして使用すると、[ライセンス条項](https://aka.ms/vsls-license)と[プライバシーに関する声明](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)に同意したものと見なされます。 問題が発生した場合は、[トラブルシューティング](../troubleshooting.md)に関するページをご覧ください。

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [省略可能] 読み取り専用ゲストとして VS Code に参加する

VS Code で、Live Share の拡張機能をインストールし、再起動し、依存関係を待機してインストールを完了すると、読み取り専用ゲストとしてコラボレーション セッションにすぐに参加できます。

> [!NOTE]
> 参加しているコードを編集する場合は、サインインする必要があります。

ブラウザーで招待リンクを開くと (または再び開くと)、ブラウザーで VS Code を起動するかどうかをたずねる通知が表示されます。 起動を許可すると、コラボレーション セッションへの接続が開始されます。

VS Code が起動すると、サインインを求めるトースト通知が届きます。 [Continue as read-only guest]\(読み取り専用ゲストとして続行\) を選択して、セッションに参加します。

![読み取り専用ゲストとしてセッションに参加するトースト](../media/vscode-read-only-guest.png)

参加者がセッション内で識別できるように表示名の入力が求められます。

![読み取り専用ゲスト名](../media/vscode-read-only-guest-name.png)

これで、読み取り専用としてセッションに参加します。 コードの表示、コード内の移動、共同デバッグ、共有サーバーと端末の表示 (読み取り専用) ができるようになります。

> [!NOTE]
> 後で、コードへの読み取り/書き込みアクセスの取得が必要になった場合には、サインインすることができます。 ステータス バーで表示名をクリックして、[サインイン] オプションを選択します。
![読み取り専用ゲストのサインイン](../media/vscode-read-only-guest-signin.png) これにより、ブラウザーが起動し、Microsoft アカウントまたは GitHub アカウントを選んでサインインできます。

## <a name="3-sign-in"></a>3.サインイン

Live Share の拡張機能をインストールし、再起動し、依存関係を待機して (VS Code の) インストールを完了したら、サインインして他の参加者に自分のことを知らせることができます。 この手順をスキップすると、参加プロセス中にサインインを求められるか、読み取り専用ゲストとしてセッションに参加できます。 [Live Share] ステータス バー項目 (VS Code) または [サインイン] ボタン (VS) をクリックして開始します。

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

**VS Code** で、お使いのブラウザーが起動し、サインインを求める通知が表示されます。 ブラウザーでのサインイン プロセスが完了したら、ブラウザーを閉じるだけです。

![Web ブラウザーを使用してサインインを求めるトースト通知](../media/vscode-sign-in-toast.png)

> **Linux ユーザー:** Live Share の古いバージョン (v0.3.295 以前) を使用している場合は、ユーザー コードの入力を求められる場合があります。 最新バージョンの拡張機能に更新するか、サインイン後に [問題が発生した場合] の リンクをクリックしてコードを表示します。 詳細については、[こちら](../use/vscode.md#sign-in-using-a-user-code)をご覧ください。

**Visual Studio** では、ユーザーの[個人アカウント](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)が Live Share によって自動的に使用されます。 その結果、いつものように簡単にサインインできます。 ただし、Visual Studio の個人アカウント以外の別のサインインを使用する場合は、**[ツール] &gt; [オプション] &gt; [Live Share] &gt; [ユーザー アカウント]** の順に移動し、別の資格情報を選択します。

まだ問題がある場合は、[トラブルシューティング](../troubleshooting.md#sign-in)を参照してください。

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4.ブラウザーで招待リンクを開く (またはもう一度開く)

ブラウザーで招待リンクを開く (またはもう一度開く) だけです。

> **注**:Live Share の拡張機能をまだインストールしていない場合は、拡張機能のマーケットプレースへのリンクが表示されます。 拡張機能をインストールしてツールを再起動して再度試します。

ブラウザーで Live Share 対応のツールを起動するかどうかをたずねる通知が表示されます。 選択したツールの起動を許可すると、起動したときにコラボレーション セッションに接続されます。

![参加ページ](../media/join-page.png)

ホストがオフラインの場合は、代わりにこの時点で通知されます。 ホストに連絡して、もう一度共有するように依頼できます。

> **トラブルシューティングのヒント:** VS Code を使用する場合は、拡張機能をインストールして、依存関係を待機してインストールが完了 (ステータス バーで確認) した後に、**ツールを少なくとも 1 回起動**したことを確認してから、招待ページを開きます (またはもう一度開きます)。 まだ問題がありますか? 詳細については、[手動での参加](../reference/manual-join.md)に関するページを参照してください。

## <a name="5-collaborate"></a>5.共同作業をする

これで完了です。 数分後には、同僚のコラボレーション セッションに接続されます。 既定では、ホストは参加する人を自動的に受け入れますが、ホストに [[Require guest approval]\(ゲストの承認が必要\)](../reference/security.md#requiring-guest-approval) が設定されている場合は、ステータス バーまたは参加ダイアログに、Live Share が参加要求に対するホストの承認を待機していることが示されます。

> **セキュリティのヒント:** コラボレーション セッションに参加するゲストとして、ホストが特定のファイルや機能に対してアクセスを制限する場合があることを理解しておく必要があります。 Live Share の一部の機能と設定のセキュリティの影響について理解したいですか。 [セキュリティ](../reference/security.md)記事を参照してください。

試してみることをいくつか次に示します。

1. プロジェクトを個別に移動して、いくつか編集をしてみる
2. JavaScript、TypeScript、C# コードの実行中の IntelliSense を確認する
3. ホストと一緒に何かを編集してみる
4. ホストが移動してさまざまなファイルを編集するときに、ホストをフォローして一緒に移動してみる
5. ホストと共同デバッグ セッションを開始してみる
6. 自分のマシンで実行されている Web アプリのようにチェックアウトできるように、サーバーの共有をホストに依頼する
7. 端末を共有してコマンドをいくつか実行するようにホストに依頼する

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。

## <a name="next-steps"></a>次の手順

詳細については、次の記事をご確認ください。

- [クイック スタート:最初のプロジェクトを共有する](share.md)
- [方法:Visual Studio Code を使用して共同作業する](../use/vscode.md)
- [方法:Visual Studio を使用して共同作業する](../use/vs.md)

関連項目

- [Live Share の接続要件](../reference/connectivity.md)
- [Live Share のセキュリティ機能](../reference/security.md)
- [言語とプラットフォームのサポート](../reference/platform-support.md)
- [拡張機能のサポート](../reference/extensions.md)
