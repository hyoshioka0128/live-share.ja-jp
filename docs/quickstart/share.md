---
title: クイック スタート - Visual Studio Live Share を共有 |Microsoft Docs
description: Visual Studio Live Share コラボレーション セッションを使用して最初のプロジェクトの共有の要約のチュートリアルです。
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
ms.openlocfilehash: 3596b25dc0d08962d7813f52549dbe6fef4f00a0
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255848"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>クイック スタート: 最初のプロジェクトを共有します。

> **注:現在、Visual Studio Live Share はプレビュー段階です。ユーザー エクスペリエンスと機能は最終版ではありません。**

Visual Studio Live Share へようこそ。 Live Share を使うと、使っているプログラミング言語や構築しているアプリの種類に関係なく、リアルタイムで他のユーザーと共同で編集したりデバッグしたりできます。 これにより、現在のプロジェクトを瞬時に安全に共有してから、必要に応じて、デバッグ セッション、ターミナルのインスタンス、localhost の Web アプリ、音声通話などを共有することができます。

開始する準備はできましたか。  チームの共同作業する必要がありますのでクイック自然でしない困難になります。 このため、Visual Studio Live Share 簡単に開始するには、職場とアイデアを共有にシームレスに開始できるようにします。

> [!TIP]
> "*独自のコラボレーション セッションに参加*" できることをご存知でしたか。 これを使うと、Live Share を独自に試したり、Visual Studio または VS Code のインスタンスを起動してリモートでそれに接続したりできます。 両方のインスタンスに同じ id を使用することもできます。 ぜひお試しください。

共有を開始する次の手順に従ってください。

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
        <a href="https://aka.ms/vsls-dl/vscode"><img src="../media/download.png" alt="Download button"></a>
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

## <a name="2-sign-in"></a>2.サインイン

Live Share の拡張機能をインストール、再起動、および依存関係 (VS Code) のインストールを完了するを待つ後、は、2 人の他の参加者にサインインします。 "Live Share"ステータス バー項目 (VS Code) をクリックするだけ/「サインイン」ボタンを開始するには、(VS)。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
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

## <a name="3-open-a-folder-project-or-solution"></a>3.フォルダー、プロジェクトまたはソリューションを開く

通常、ワークフローを使用して、フォルダー、プロジェクト、または Visual Studio または Visual Studio Code で共有するソリューションを開きます。

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [省略可能] の更新プログラム ファイルを除外する/非表示

既定で Live Share**を非表示に**ゲストからの共有フォルダーの .gitignore ファイルで参照されているファイル/フォルダー。 **非表示**ファイルは、ゲストのファイル ツリーに表示されないようにします。 **除く**をファイルには、Live Share を定義またはデバッグまたは「準拠」の中に、ファイルにステップするかどうかに go ような状況でゲストを開けないようにより厳密なルールが適用されます。 別のファイルを非表示にする/除外する場合、 **. vsls.json**ファイルは、これらの設定を使用してプロジェクトに追加できます。 参照してください[ファイルへのアクセスと可視性を制御する](../reference/security.md#controlling-file-access-and-visibility)詳細についてはします。

## <a name="5-start-a-collaboration-session"></a>5.コラボレーション セッションを開始します。

次に、単に、ツール内で"Live Share"をクリックし、招待のリンクが自動的にクリップボードにコピーします。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> 初めてを共有するポートを開く Live 共有エージェントを許可するには、デスクトップのファイアウォール ソフトウェアによる求められること可能性があります。 これを受け入れるは完全に省略可能ですが、セキュリティで保護された「ダイレクト モード」を有効にしている場合に使用している人が同じネットワーク上がパフォーマンスを向上させる。 参照してください[接続モードを変更](../reference/connectivity.md#changing-the-connection-mode)詳細についてはします。

## <a name="6-optional-enable-read-only-mode"></a>6. [省略可能] を有効にする読み取り専用モード

コラボレーション セッションを開始するとは、ゲストが共有されているコードを編集したことを防ぐために読み取り専用にするセッションを設定できます。

後の共有、招待のリンクをクリップボードにコピーされたことの通知が表示されます。 読み取り専用セッションを作成するオプションを選択することができます。

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

**VS Code**、Live Share viewlet タブから読み取り専用セッションを開始することもできます。

![Web ブラウザーを使用してサインインするよう求めるトースト通知](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7.招待のリンクを送信する.

招待する場合に Skype などで Slack、電子メール経由でのリンクを送信します。 ブラウザーで、リンクを開くと、フォルダー、プロジェクト、または開いたソリューションの内容を共有している共同作業セッションに参加することができます。 なおのレベルに、Live Share セッションは、ゲストに提供できるアクセス**のみを信頼できるユーザーと共有する必要があります**と共有している場合の影響を十分に検討します。

> **セキュリティのヒント:** Live Share の機能の一部のセキュリティの影響について理解をしますか。 チェック アウト、[セキュリティ](../reference/security.md)記事。

招待したゲスト、質問がある場合、[クイック スタート。最初のセッションに参加](join.md)資料取得すると、ゲストとして実行されているいくつかの詳細を提供します。

## <a name="8-optional-approve-the-guest"></a>8. (省略可能) 承認ゲスト

既定では、ゲストが、コラボレーション セッションを自動的に参加して、お客様と協力する準備ができているときに通知されます。

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

代わりに参加するすべてのユーザーの明示的な「承認」を要求するように選択することができます。 この設定を有効にした場合、通知では、セッションに参加しようとすると、ゲストを承認するように求められます。

参照してください[ゲストの承認を必要とする](../reference/security.md#requiring-guest-approval)この機能を有効にする方法の詳細について。

## <a name="9-collaborate"></a>9.共同作業を行います。

これで完了です。 ゲストが参加すると、試し、いくつかの事項を次に示します。

1. プロジェクト内の別のファイルを個別に移動し、いくつかの編集を行う
1. 次のゲストと観察スクロール、編集を加えて、および異なるファイルに移動します
1. それらに同じデバッグ セッションを開始します。
1. サーバーで共有されるため、自分のマシンで実行されている web アプリのようなものを確認できます。
1. ターミナルを共有し、いくつかのコマンドを実行

チェック アウト、 [Visual Studio Code](../use/vscode.md)と[Visual Studio](../use/vs.md)これらのアクションを実行する方法についての拡張機能のドキュメント。

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。

## <a name="next-steps"></a>次の手順

詳細についてはこれらの記事を確認します。

- [クイック スタート:最初の共同作業セッションに参加します。](join.md)
- [方法:Visual Studio Code を使用して共同作業します。](../use/vscode.md)
- [方法:Visual Studio を使用して共同作業します。](../use/vs.md)

参照

- [Live Share の接続要件](../reference/connectivity.md)
- [Live Share のセキュリティ機能](../reference/security.md)
- [言語とプラットフォームのサポート](../reference/platform-support.md)
- [拡張機能のサポート](../reference/extensions.md)
