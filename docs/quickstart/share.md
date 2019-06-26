---
title: 共有のクイック スタート - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share コラボレーション セッションを使用して、初めてプロジェクトを共有するための簡単なチュートリアルです。
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
ms.openlocfilehash: e65656c604a9dbc479a03a503fe01d7e2d938072
ms.sourcegitcommit: c702aafb65b0fc43cb210e1bb7340cef48b57f35
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "67322792"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>クイック スタート: 最初のプロジェクトを共有する

Visual Studio Live Share へようこそ。 Live Share を使うと、使っているプログラミング言語や構築しているアプリの種類に関係なく、リアルタイムで他のユーザーと共同で編集したりデバッグしたりできます。 これにより、現在のプロジェクトを瞬時に安全に共有してから、必要に応じて、デバッグ セッション、ターミナルのインスタンス、localhost の Web アプリ、音声通話などを共有することができます。

開始する準備はできましたか。  チーム コラボレーションはすばやく自然に行える必要があり、そうでないとより困難になります。 このため、Visual Studio Live Share はそれを簡単に始められるようにして、仕事とアイデアをシームレスに共有できるようにします。

> [!TIP]
> "*独自のコラボレーション セッションに参加*" できることをご存知でしたか。 これを使うと、Live Share を独自に試したり、Visual Studio または VS Code のインスタンスを起動してリモートでそれに接続したりできます。 両方のインスタンスで同じ ID を使用することもできます。 ぜひお試しください。

次の手順に従って共有を開始します。
<!--
Change the instructions to Install extension for VS Code and in-tool for VS?
-->
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
        <a href="https://aka.ms/vsls-dl/vscode"><img src="../media/download.png" alt="Download button"></a>
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

## <a name="2-sign-in"></a>2.サインイン

<!--
Re-write the grammar here- run on sentence does not make sense. Change screen shots. There is another way of signing in as well- what if a user goes directly to the start collaboration. 
-->
Live Share の拡張機能をインストールし、再起動し、依存関係を待機して (VS Code の) インストールを完了したら、サインインして他の参加者に自分のことを知らせることができます。 [Live Share] ステータス バー項目 (VS Code) または [サインイン] ボタン (VS) をクリックして開始します。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button-new.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

**VS Code** で、お使いのブラウザーが起動し、サインインを求める通知が表示されます。 ブラウザーでのサインイン プロセスが完了したら、ブラウザーを閉じるだけです。

![Web ブラウザーを使用してサインインを求めるトースト通知](../media/vscode-sign-in-toast.png)

> **Linux ユーザー:** Live Share の古いバージョン (v0.3.295 以前) を使用している場合は、ユーザー コードの入力を求められる場合があります。 最新バージョンの拡張機能に更新するか、サインイン後に [問題が発生した場合] の リンクをクリックしてコードを表示します。 詳細については、[こちら](../use/vscode.md#sign-in-using-a-user-code)をご覧ください。

**Visual Studio** では、ユーザーの[個人アカウント](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)が Live Share によって自動的に使用されます。 その結果、いつものように簡単にサインインできます。 ただし、Visual Studio の個人アカウント以外の別のサインインを使用する場合は、 **[ツール] &gt; [オプション] &gt; [Live Share] &gt; [ユーザー アカウント]** の順に移動し、別の資格情報を選択します。

まだ問題がある場合は、[トラブルシューティング](../troubleshooting.md#sign-in)を参照してください。

## <a name="3-open-a-folder-project-or-solution"></a>3.フォルダー、プロジェクト、またはソリューションを開く

通常のワークフローを使用して、Visual Studio または Visual Studio Code で共有するフォルダー、プロジェクト、またはソリューションを開きます。

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [省略可能] 非表示または除外されているファイルを更新する

既定では、Live Share は共有フォルダー内の .gitignore ファイルで参照されているすべてのファイル/フォルダーをゲストから**非表示**にします。 ファイルを**非表示**にすることで、ゲストのファイル ツリーにそのファイルが表示されないようにします。 ファイルの**除外**は、定義に移動するような状況や、デバッグ中または "フォロー中" のファイルにステップ インした場合に、Live Share がゲストにそのファイルを開かないようにする、より厳格な規則を適用します。 別のファイルを非表示/除外する場合は、これらの設定を使用して **.vsls.json** ファイルをプロジェクトに追加できます。 詳細については、[ファイルのアクセスと可視性を制御する](../reference/security.md#controlling-file-access-and-visibility)のセクションを参照してください。

## <a name="5-start-a-collaboration-session"></a>5.コラボレーション セッションを開始する

<!--
-->
次に、ツール内で [Live Share] をクリックします。招待リンクが自動的にクリップボードにコピーされます。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button-new.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> 初めてを共有するときに、Live Share エージェントがポートを開くのを許可するように、デスクトップのファイアウォール ソフトウェアから求められる場合があります。 これを受け入れるかどうかは任意ですが、共同作業する人が同じネットワーク上にいるときには、セキュリティで保護された "ダイレクト モード" を有効にしてパフォーマンスを向上させます。 詳細については、[接続モードを変更する](../reference/connectivity.md#changing-the-connection-mode)のセクションを参照してください。

## <a name="6-optional-enable-read-only-mode"></a>6. [省略可能] 読み取り専用モードを有効にする

コラボレーション セッションを開始したら、セッションを読み取り専用に設定して、ゲストが共有中のコードを変更できないようにすることができます。

共有後、招待リンクがクリップボードにコピーされたことを知らせる通知が表示されます。 オプションを選択して、セッションを読み取り専用にすることができます。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-read-only-toast.png" width="100%" alt="Visual Studio Code read-only option" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-read-only-notification.png" width="100%" alt="Visual Studio read-only option"/>
    </td>
</tr>
</table>

**VS Code** では、Live Share の viewlet タブから読み取り専用セッションを開始することもできます。

![Web ブラウザーを使用してサインインを求めるトースト通知](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7.招待リンクを送信する

電子メール、Slack、Skype などを使用して、招待したい人にリンクを送信します。 受信した人がブラウザーでリンクを開くと、あなたが開いたフォルダー、プロジェクト、またはソリューションの内容を共有しているコラボレーション セッションに参加することができます。 Live Share セッションがゲストに提供できるアクセス レベルを考慮すると、**信頼できる人とだけ共有**するように注意してください。また、共有するものの影響を十分に検討してください。

> **セキュリティのヒント:** Live Share の一部の機能のセキュリティの影響について理解したいですか。 [セキュリティ](../reference/security.md)記事を参照してください。

招待したゲストが質問がある場合は、「[クイック スタート:最初のセッションに参加する](join.md)」の記事で、ゲストとして開始および実行することについて、もう少し詳しい情報が得られます。

## <a name="8-optional-approve-the-guest"></a>8. [省略可能] ゲストを承認する

既定では、ゲストはコラボレーション セッションに自動的に参加し、ゲストが共同作業の準備ができると、通知されます。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

代わりに、参加する人全員に明示的な "承認" を求めるように選択することもできます。 この設定を有効にすると、ゲストがセッションに参加しようとしたときに、ゲストの承認を促す通知が表示されます。

この機能を有効にする詳しい方法については、[ゲストの承認を要求する](../reference/security.md#requiring-guest-approval)のセクションを参照してください。

## <a name="9-collaborate"></a>9.共同作業をする

これで完了です。 ゲストが参加したら、試してみることをいくつか次に示します。

1. プロジェクト内のさまざまなファイルを個別に移動して、いくつか編集をしてみる
1. ゲストがスクロール、編集、別のファイルに移動したときに、ゲストをフォローして観察してみる
1. ゲストと共同デバッグ セッションを開始してみる
1. ゲストのマシンで実行されている Web アプリのようにチェックアウトできるように、サーバーを共有する
1. ターミナルを共有してコマンドをいくつか実行してみる

これらのアクションを実行する方法などの詳細は、[Visual Studio Code](../use/vscode.md) と [Visual Studio](../use/vs.md) 拡張機能のドキュメントをご確認ください。

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。

## <a name="next-steps"></a>次の手順

詳細については、次の記事をご確認ください。

- [クイック スタート:コラボレーション セッションに初めて参加する](join.md)
- [方法:Visual Studio Code を使用して共同作業する](../use/vscode.md)
- [方法:Visual Studio を使用して共同作業する](../use/vs.md)

関連項目

- [Live Share の接続要件](../reference/connectivity.md)
- [Live Share のセキュリティ機能](../reference/security.md)
- [言語とプラットフォームのサポート](../reference/platform-support.md)
- [拡張機能のサポート](../reference/extensions.md)
