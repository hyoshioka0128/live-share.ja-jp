---
title: トラブルシューティング-Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live Share のトラブルシューティングのヒントとコツ。
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: troubleshooting
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: afa11a77156fd0227c9d9cfd5ce701ae0211386e
ms.sourcegitcommit: 5e0d384c71793a83b58023352f56f0a24783a2e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72531045"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>Visual Studio Live Share のトラブルシューティング

この記事では、トラブルシューティングのヒント、回避策、一般的な問題と質問に対する回答について説明します。 [FAQ](faq.md)を参照することもできます。 

## <a name="installation--tool-requirements"></a>インストール/ツールの要件

Visual Studio Live Share のインストールに関連するトラブルシューティングのヒントを次に示します。

| ツール | 問題 | 解決策/回避策 |
|------|---------|------------|
| VS | 拡張機能のインストーラーで、Visual Studio Live Share 拡張機能をインストールしようとしたときに使用する<strong>Visual Studio のバージョンが見つかりません</strong>。 | Visual Studio Live Share には、ホストとゲストの両方に対して**Visual Studio 2017 バージョン 15.6**以降が必要です。 [Visual Studio 2017 の最新の](https://visualstudio.com/vs/)安定した更新プログラムをインストールして、再試行してください。|
| VS Code | MacOS <strong>El Capitan 以下</strong>で VS Code で Visual Studio Live Share を使用しようとすると、エラーが表示されます。 | Visual Studio Live Share の OS サポートは[、現在 macOS Sierra をサポート](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)している .net Core に依存しています。 |
| VS Code | "**依存関係をインストールできませんでした**" というエラーが表示されますが、拡張機能は最初の起動時に**インストールを完了**しているか、存在し**ないか、既に存在するファイル**に関するエラーが発生します。 | **ネットワーク接続が良好**であることを確認します。 お持ちの場合は、**プロキシまたはファイアウォール**の問題が発生している可能性があります。 「[接続のトラブルシューティング](#connectivity)」を参照してください。 <br /><br />|
| VS Code | Marketplace から Visual Studio Live Share 拡張機能をインストールすると、必要なバージョンではなく<strong>VS Code の安定したバージョンに</strong>インストールされます。 | 安定した VS Code または insider を開始するには、好みに応じて [拡張機能] タブをクリックし、"Visual Studio Live Share" を検索してそこからインストールします。 |
| VS Code (**Linux**) | Live Share 拡張機能がアクティブ化されず、 **Linux**に拡張機能をインストールした後に**ステータスバー項目が表示さ**れません。 | Visual Studio Live Share は、既定で Linux の特定のディストリビューションで満たされない可能性がある多くの Linux 前提条件を持つ .NET Core 2.0 に依存しています。 インストールする内容の[詳細については、こちらを](reference/linux.md#install-linux-prerequisites)参照してください。 |

## <a name="sign-in"></a>サインイン

サインインの問題に関するトラブルシューティングのヒントを次に示します。

| ツール | 問題 | 解決策/回避策 |
|------|---------|------------|
| VS | Visual Studio へのサインインに使用したものとは<strong>異なる id</strong>を使用して Visual Studio Live Share にサインインする必要があります。 | ツール > オプション > Live Share > ユーザーアカウント にアクセスして、別のアカウントを選択します。 |
| VS Code | サインイン時にブラウザーウィンドウが<strong>表示され、web ページで</strong>プロセスが成功したように見える場合でも、ブラウザーを閉じた後もステータスバーに<strong>"サインイン"</strong>と表示されます。 | サインインしたら、[問題が発生していますか?] をクリックします。 指示に従って、ツールに一時的なユーザーコードを入力します。<br /><br />また、何が起こっているかを確認したいので、[バグをログに記録](https://aka.ms/vsls-problem)してください。 |
| すべて | <strong>タイムアウトまたは接続エラーが発生</strong>しています。 | 「[接続のトラブルシューティング](#connectivity)」を参照してください。 |
| すべて | Microsoft の**勤務先または学校の電子メールアドレス**を使用してサインインすると、 **"管理者の承認が必要です"** というメッセージが表示されます。 | Azure AD の理念は、ディレクトリの内容にアクセスする新しいアプリケーションに対して "管理者の同意" を要求するように設定されています。 詳細について[は、こちら](reference/security.md)を参照してください。 |
| VS Code (**macOS**) | サインインすると、 **SecKeychainAddGenericPassword () が失敗した**ことを示すエラーが表示されます。 | これは、ほとんどの場合、パスワードの変更がログインキーチェーンに反映されない macOS に関する一般的な問題が原因です。 "キーチェーンアクセス" に移動し、ログインキーチェーンをロックしてから、もう一度ロックを解除してください。 これは問題を解決するのに十分な場合がありますが、現在のパスワードを使用してロックを解除できない場合は、前のパスワードを試してください。 その場合は、ログインキーチェーンパスワードを現在のパスワードに変更します。 詳細について[は、こちら](https://support.apple.com/en-us/HT201609)を参照してください。 |
| VS Code (**Linux**) | ブラウザーを使用してサインインした後、ユーザーコードに入力すると、 **secret_password_store_sync () がエラーコード XX で失敗**したことを示すエラーが表示されます。 | これは、通常、`gnome-keyring` または `libsecret-1-0` /  `libsecret` インストールされていないことが原因です。 @No__t_0 をインストールし、デスクトップ環境で "パスワードとキー" アプリケーションを使用することによって、gnome キーリングが正しく構成されていることを確認できます。 [Linux の前提条件](reference/linux.md#install-linux-prerequisites)の詳細については、こちらを参照してください。 |
| VS Code (**Linux**) | Live Share v 0.3.295 以下の<strong>ユーザーコードを入力する</strong>ように求められますが、ブラウザーを取得できません。 | Linux でのユーザーコードの要件をなくすために取り組んでいます。 平均時間では、サインインに使用するブラウザーウィンドウが表示されます。 それ以外の場合は、[VS Code] の下にブラウザーウィンドウが非表示になっている可能性があります。 そうでない場合は、次のヒントを参照してください。  |
| VS Code | [サインイン] をクリックするか (または、[Live Share: サインイン] コマンドを使用して)、<strong>資格情報を入力できるブラウザーウィンドウが表示されません</strong>。 | 1.[ここにサインイン](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)します<br />2. サインインした後、[問題が発生していますか?] をクリックします。<br /> 3. 指示に従って、ツールに一時的なユーザーコードを入力します。 |
| すべて | コラボレーションセッションに<strong>参加</strong>しようとしていますが、<strong>電子メールの更新プログラムを受信しない</strong>ようにします。 </strong>。 | VS/VS Code の Live Share 拡張機能にサインインしても、電子メールの更新を受け取ることはでき<strong>ません</strong>。<br /><br />Live Share には、ゲストがセキュリティ対策としてサインインし、ホストが参加している id を認識できるようにする必要があります。 [この機能](https://github.com/MicrosoftDocs/live-share/issues/3)は、匿名ユーザーが参加することを許可するオプションを希望する場合に投票します (たとえば、名前/ユーザー定義名がないユーザー)。 |

## <a name="share-and-join"></a>共有と参加

サインインの問題に関するトラブルシューティングのヒントを次に示します。

| ツール | 問題 | 解決策/回避策 |
|------|----------------|------------|
| すべて | <strong>共有/結合:</strong>接続できないことに関するタイムアウトまたはエラーが発生しています。 | 「[接続のトラブルシューティング](#connectivity)」を参照してください。 |
| VS Code | <strong>結合:</strong>ブラウザーで参加ページを開いた後<strong>に、VS Code を起動するかどうかを確認するメッセージも表示されません</strong>でした。 |  ヒント: <ul><li>VS Code を少なくとも<i>1 回開始し、ステータスバーでインストールが完了するのを待っ</i>ていることを確認してください。</li><li>それでもうまくいかない場合は、"Live Share: ランチャー Setup" コマンドを実行してみてください。</li><li>**Linux ユーザー**: 上記のコマンドの実行時に管理者 (sudo) のパスワードの入力を求められた場合は、それを実行してください。</li><li>最後に、「回避策として[手動で参加](reference/manual-join.md)する」を参照してください。</li></ul> この問題が発生した場合は、何が起こっているかを確認することをお勧めします。[バグをログに記録](https://aka.ms/vsls-new-issue)してください。 |
| VS | <strong>結合:</strong>ブラウザーで参加ページを開いた後、 <strong>VS を起動するように求められません</strong>でした。 |  「[手動で参加する](reference/manual-join.md)」を参照してください。<br /><br /> また、ログを確認することもできます。そのため、Visual Studio の [問題の報告] を使用して[バグをログに記録](https://aka.ms/vsls-problem)してください。機能. |
| すべて | <strong>結合:</strong>Web リンクをクリックするのではなく、 <strong>Visual Studio/VS Code に直接結合リンクを貼り付ける</strong>ことをお勧めします。 | 「[手動で参加する](reference/manual-join.md)」を参照してください。 |
| すべて | <strong>結合:</strong>ブラウザーを使用して参加すると、"**ワークスペースの所有者はオフラインです**" というメッセージが表示されます。 | 考えられる回避策:<br /><ul><li>[手動で参加](reference/manual-join.md)してみてください。 手動結合に影響を与えないサービスの問題により、リージョン間 (東や米国西部など) の参加に関する問題が発生しました。</li><li>Live Share が "自動" 接続モードで実行されている場合、ホストに直接ルーティングできない可能性があります。 [リレーモード](reference/connectivity.md)をお試しください。</li></ul>詳細については、「[接続のトラブルシューティング](#connectivity)」をご覧ください。 |
| VS Code | <strong>結合:</strong>サインインする<strong>前</strong>にブラウザーを介して参加しました。 </strong> サインインするように求められませんでした。参加は完了していません。 |  これは[既知のバグ](https://github.com/MicrosoftDocs/live-share/issues/167)です。 サインインのステータスバー項目をクリックしてサインインし、もう一度参加します。 |

## <a name="connectivity"></a>接続

次の情報は、サインイン、共有、または参加時の接続またはタイムアウトに関する問題が発生している場合のトラブルシューティングに役立ちます。

[Live Share 記事の接続要件](reference/connectivity.md)に記載されているように、さまざまな接続モードが機能するための要件が異なるため、いくつかの潜在的な問題が発生します。

| ツール | 問題 | 考えられる原因 |
|------|------|----------------|
| すべて | <strong>プロキシ</strong>を使用していて、多数の接続の問題が発生している | プロキシ設定は、複雑になる可能性があります。  **HTTP_PROXY**環境変数と**HTTPS_PROXY**環境変数を**グローバル**に設定してから、ツールを再起動してみてください。 詳細については、[プロキシ設定](reference/connectivity.md#proxies)を参照してください。 まだサポートされていない構成が存在する可能性があるため、これがうまくいか[ない場合はお知らせください](https://github.com/MicrosoftDocs/live-share/issues/86)。 |
| VS Code | 拡張機能をインストールしてから VS Code を起動した後、 <strong>[インストールの完了] がステータスバーに表示されたときにエラーが表示され</strong>ます。 |  個人または企業のファイアウォールによってポート443がブロックされている場合、インターネットにアクセスしたり、download.visualstudio.microsoft.com や download.microsoft.com にアクセスしたりすることはできません。 この時点で Live Share をダウンロードする必要がある理由について[は、こちら](https://github.com/MicrosoftDocs/live-share/issues/58)を参照してください。 |
| すべて | <strong>サインインできません Visual Studio Live Share</strong> | ポート80/443 では、個人または企業のファイアウォールによってブロックされているため、インターネットにアクセスできないか、または *. liveshare.vsengsaas.visualstudio.com にアクセスできません。 ブラウザーで https://insiders.liveshare.vsengsaas.visualstudio.com を入力し、Visual Studio Live Share のホームページに移動していることを確認します。 |
| すべて | <strong>自動モード</strong>(既定) ではサインインできますが、共有または参加時に<strong>タイムアウトまたは接続エラー</strong>が表示されます。 | 直接モードとリレーモードのどちらも接続に失敗しているか、auto モードでバグが発生しています。 [直接モードまたはリレーモードに切り替え](reference/connectivity.md#changing-the-connection-mode)た後に接続できる場合は、[バグを発生させ](https://aka.ms/vsls-problem)てください。 |
| すべて | <strong>直接モード</strong>ではサインインできますが、共有または参加時に<strong>タイムアウトまたは接続エラーが発生</strong>します。 | ゲストとホストは直接接続できません。 [自動モードまたはリレーモード](reference/connectivity.md#changing-the-connection-mode)を試して、問題が解決しないかどうかを確認します。 場合によっては[、個人のファイアウォールで Live Share を手動で許可](reference/connectivity.md#manually-adding-a-firewall-entry)するか、リレーモードを使用する必要があります。 |
| すべて | <strong>リレーモード</strong>ではサインインできますが、共有または参加時に<strong>タイムアウトまたは接続エラー</strong>が通知されます。 | ポート80/443 の *. servicebus.windows.net へのアクセスはブロックされています。これは、個人または企業のファイアウォールによってブロックされています。 [Direct モード](reference/connectivity.md#changing-the-connection-mode)をお試しください。 |

接続要件の詳細については、 [Live Share の接続要件](reference/connectivity.md)に関する記事を参照してください。

## <a name="see-also"></a>関連項目

クイックスタート

- [最初のプロジェクトを共有する](quickstart/share.md)
- [最初のセッションに参加する](quickstart/join.md)

方法

- [Visual Studio Code を使用して共同作業する](use/vscode.md)
- [Visual Studio を使用して共同作業する](use/vs.md)

参照

- [すべての主要なバグ、機能要求、および制限事項](https://aka.ms/vsls-issues)
- [すべての機能要求および制限事項](https://aka.ms/vsls-feature-requests)
- [Live Share の接続要件](reference/connectivity.md)
- [Linux インストールの詳細](reference/linux.md)
- [言語とプラットフォームのサポート](reference/platform-support.md)
- [拡張機能のサポート](reference/extensions.md)

それでも問題が発生する場合は、 フィードバックを[提供](support.md)することができます。
