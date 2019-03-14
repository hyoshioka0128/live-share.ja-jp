---
title: トラブルシューティング - Visual Studio の Live Share |Microsoft Docs
description: トラブルシューティングのヒントとテクニックについては、Visual Studio Live Share
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: troubleshooting
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 8d20ec73d9cadfefced65c04b1ef18f6e844167d
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255875"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>トラブルシューティングの Visual Studio Live Share

この記事では、トラブルシューティングのヒント、回避策、および一般的な問題と質問の回答について説明します。 確認することも、 [FAQ](faq.md)します。

## <a name="installation--tool-requirements"></a>インストール要件をツール/

トラブルシューティングの Visual Studio Live Share をインストールに関連するヒントを次にします。

| ツール | 問題 | 解決または回避策 |
|------|---------|------------|
| VS | 拡張機能インストーラー <strong>Visual Studio のバージョンを見つけることができません</strong>Visual Studio Live Share の拡張機能をインストールしようとしたときに使用します。 | Visual Studio Live Share 必要**Visual Studio 2017 バージョン 15.6**以上のホストとゲストの両方。 最新の安定したインストール[Visual Studio 2017 の更新プログラム](https://visualstudio.com/vs/)再試行してください。|
| VS Code | MacOS で VS Code と Visual Studio Live Share を使用しようとするときにエラーが表示されます<strong>El Capitan 以下</strong>します。 | Visual Studio Live Share の OS のサポートは、.NET Core に依存している現在[macOS Sierra のみをサポート以降。]((https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).) |
| VS Code | A"**依存関係をインストールできませんでした**"実行中にエラーが表示されます拡張機能は**インストールの完了**最初に開始するかエラーが発生**見つからなかったりファイルが既に存在します**. | 使用していることを確認、**良好なネットワーク接続**します。 可能性がありますに実行する場合を**プロキシまたはファイアウォール**問題。 参照してください[接続のトラブルシューティング](#connectivity)します。 <br /><br />|
| VS Code | Marketplace から、Visual Studio Live Share の拡張機能をインストールする<strong>その VS Code の/内部関係者が安定したバージョンにインストール</strong>は目的のバージョンではなく。 | VS Code の安定版または好みに応じて内部関係者を開始、"extensions" タブをクリックして、"Visual Studio Live Share"を検索およびそこからインストールします。 |
| VS Code (**Linux**) | Live Share の拡張機能がアクティブにならないと**ステータス バーの項目が表示されない**に拡張機能をインストールした後**Linux**します。 | Visual Studio Live Share は、さまざまな既定の Linux の特定のディストリビューションで満たされる可能性はない Linux の前提条件のある .NET Core 2.0 に依存します。 参照してください[詳細についてはここで](reference/linux.md#install-linux-prerequisites)で何をインストールする必要があります。 |

## <a name="sign-in"></a>サインイン

トラブルシューティングのサインインに関する問題のためのヒントを次にします。

| ツール | 問題 | 解決または回避策 |
|------|---------|------------|
| VS | Visual Studio Live Share にサインインする必要がある、<strong>さまざまな id</strong> Visual Studio へのサインインに使用するとします。 | ツール > オプション > Live Share > ユーザー アカウントを別のアカウントを選択します。 |
| VS Code | サインイン時にブラウザーのウィンドウの pop とプロセス中に<strong>は web ページで成功</strong>、ステータス バー<strong>前、「サインイン」</strong>ブラウザーを閉じた後。 | サインインした後、「問題が発生しますか?」をクリックします ツールに一時的なユーザー コードを入力する手順に従います。<br /><br />何可能性がありますが起こっているか、これを参照してくださいにも加わってください[バグのログ記録](https://aka.ms/vsls-problem)します。 |
| すべて | 取得する、<strong>タイムアウトまたは接続エラー</strong>します。 | 参照してください[接続のトラブルシューティング](#connectivity)します。 |
| すべて | バックアップ、Microsoft を使ってサインインするときに**職場または学校の電子メール アドレス**というメッセージが表示 **「管理者の承認が必要」** します。 | Azure AD テナントとは、ディレクトリの内容にアクセスする新しいアプリケーションの「管理者の同意」を要求するセットアップです。 参照してください[ここ](reference/security.md)の詳細。 |
| VS Code (**macOS**) | 示すエラーが出力するサインイン**失敗 SecKeychainAddGenericPassword()** します。 | これはほぼ常に macOS の一般的な問題が原因、パスワードの変更はログイン キーチェーンで反映されません。 [キーチェーン アクセス] に、ログイン キーチェーンをロックして、もう一度ロック解除してください。 これだけで、問題を解決するには、現在のパスワードでロックを解除されない場合は、前のものをお試しください場合があります。 成功した場合は、現在のパスワード ログイン キーチェーンのパスワードを変更します。 参照してください[ここ](https://support.apple.com/en-us/HT201609)詳細についてはします。 |
| VS Code (**Linux**) | ブラウザーを使用してサインインした後、ユーザー コードで入力するときに、というエラーが表示**secret_password_store_sync() 失敗して、エラー コード XX**します。 | これは、通常原因`gnome-keyring`や`libsecret-1-0` /  `libsecret`インストールされていません。 Gnome キーリングを検証することができますが、インストールすることで正しく構成されて`seahorse`とデスクトップ環境で「パスワードとキー」アプリケーションを使用します。 詳細をご覧ください[Linux の前提条件をここで](reference/linux.md#install-linux-prerequisites)します。 |
| VS Code (**Linux**) | したら<strong>ユーザー コードを入力するように求め</strong>Live Share v0.3.295 以下がいずれかを取得するようにブラウザーは表示されません。 | Linux 上のユーザー コードいいように取り組んでいます。 までの平均時間を使用してサインインするためのブラウザー ウィンドウを表示します。 それ以外の場合は、VS Code で、ブラウザー ウィンドウを非表示にすることがあります。 そうでない場合は、次のヒントを参照してください。  |
| VS Code | [サインイン] をクリックした後 (またはを使用して、"ライブ共有。Sign in"コマンド)、<strong>資格情報を入力するようにブラウザーのウィンドウは表示されない</strong>します。 | 1.[ここでサインインします。](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)<br />2.サインインした後、「問題が発生しますか?」をクリックします<br /> 3.ツールに一時的なユーザー コードを入力する手順に従います。 |
| すべて | たい<strong>結合</strong>コラボレーション セッション</strong>が<strong>されませんが、電子メールの更新プログラムを受信したくない/</strong>します。 | VS/VS Code での Live Share の拡張機能へのサインインは<strong>いない</strong>受信電子メールの更新プログラムに参加することです。<br /><br />ライブの共有には、ゲストをホストに参加しているものの id に可視性を持っているため、セキュリティ対策としてサインインする必要があります。 [この機能に投票する](https://github.com/MicrosoftDocs/live-share/issues/3)匿名ユーザーの参加を許可するオプションが希望されるかどうか (名前のないユーザーなど、ユーザー定義名/)。 |

## <a name="share-and-join"></a>共有と結合

トラブルシューティングのサインインに関する問題のためのヒントを次にします。

| ツール | 問題 | 解決または回避策 |
|------|----------------|------------|
| すべて | <strong>共有/結合。</strong>タイムアウトまたは接続できないというエラーが発生します。 | 参照してください[接続のトラブルシューティング](#connectivity)します。 |
| VS Code | <strong>Join:</strong>した<strong>いないメッセージを表示/VS Code を起動できません</strong>[参加] ページをブラウザーで開いた後です。 |  ヒント: <ul><li>したかどうかを必ず<i>を少なくとも 1 回、VS Code を起動し、インストールをステータス バーに完了するを待機します。</i></li><li>うまく行かない場合は、実行してみてください、"ライブ共有。「ランチャー セットアップ コマンド。</li><li>**Linux ユーザー**:上記のコマンドを実行するときに、管理者 (sudo) パスワードを入力するように求められたら、これを行ってください。</li><li>最後を参照してください[手動による結合](reference/manual-join.md)問題を回避します。</li></ul> この問題が発生した場合は、何可能性がありますが起こっているか、これを参照してください。 ぜひください[バグのログ記録](https://aka.ms/vsls-new-issue)します。 |
| VS | <strong>Join:</strong>した<strong>メッセージを表示/VS を起動することができません</strong>[参加] ページをブラウザーで開いた後です。 |  参照してください[を手動で結合](reference/manual-join.md)します。<br /><br /> そのため、ログを参照してくださいにも加わってください[バグのログ記録](https://aka.ms/vsls-problem)Visual Studio の [レポートの問題] を使用します。機能です。 |
| すべて | <strong>Join:</strong>希望する<strong>Visual Studio に直接結合のリンクを貼り付ける/コードを VS</strong> web リンクをクリックするのではなく。 | 参照してください[を手動で結合](reference/manual-join.md)します。 |
| すべて | <strong>Join:</strong>というメッセージを参照してください"**、ワークスペースの所有者がオフラインになるよう**、"ブラウザー経由で結合するとき。 | 可能な回避策:<br /><ul><li>お試しください[手動による結合](reference/manual-join.md)します。 リージョン間での問題が検出された (例: east および west 米国) 結合を手動での結合に影響しないサービスの問題が原因です。</li><li>ライブの共有は、"auto"接続モードで実行する場合は、ホストに直接ルーティングすることができない可能性があります。 お試しください[リレー モード](reference/connectivity.md)します。</li></ul>参照してください[接続のトラブルシューティング](#connectivity)可能性について |
| VS Code | <strong>Join:</strong>ブラウザー経由で参加している<strong>サインインする前に</strong>、サインインするように要求されなかった場合</strong>、し、結合が完了したことはありません。 |  これは、[既知のバグ](https://github.com/MicrosoftDocs/live-share/issues/167)します。 サインインにサインインして、もう一度参加し、ステータス バーの項目をクリックします。 |

## <a name="connectivity"></a>接続

以下の情報を共有、またはへの参加、サインインするときに、タイムアウトまたは接続に関連する問題が発生する場合のトラブルシューティングできます。

」の説明に従って、 [Live Share の接続要件](reference/connectivity.md)記事では、別の接続モード要件があるさまざまな機能にいくつかの異なる潜在的な問題があるためです。

| ツール | 問題 | 考えられる原因 |
|------|------|----------------|
| すべて | 使用している、<strong>プロキシ</strong>との接続の問題の数が表示されます | プロキシの設定は難しくなってきます。  設定を試みてください、 **HTTP_PROXY**と**HTTPS_PROXY**環境変数**グローバル**し、ツールを再起動します。 参照してください[プロキシ設定](reference/connectivity.md#proxies)の詳細。 まだはサポートされていません、いくつかの構成が残っているため、[お知らせ](https://github.com/MicrosoftDocs/live-share/issues/86)がこれが機能しない場合。 |
| VS Code | 取得する拡張機能をインストールし、VS Code を初めて起動した後、 <strong>「インストールの完了」がステータス バーに表示する場合はエラー</strong>します。 |  インターネットや download.visualstudio.microsoft.com へのアクセスにアクセスすることはできませんまたは download.microsoft.com ポート 443 では、個人または会社のファイアウォールによってブロックされます。 参照してください[ここ](https://github.com/MicrosoftDocs/live-share/issues/58)理由についての Live Share はこの時点で何かをダウンロードする必要があります。 |
| すべて | したら<strong>Visual Studio Live Share にサインインすることができません</strong> | アクセスまたはインターネットにアクセスすることはできません *. liveshare.vsengsaas.visualstudio.com 80/443 が個人または会社のファイアウォールによってブロックされているポート。 入力 https://insiders.liveshare.vsengsaas.visualstudio.comブラウザーで、Visual Studio Live Share ホーム ページに着陸したことを確認します。 |
| すべて | <strong>Auto モード</strong>(既定値) で、サインインしますが、表示することが、<strong>タイムアウトまたは接続エラー</strong>または共有のいずれかに参加するときにします。 | いずれか両方ダイレクトし、リレー モードは、接続に失敗、または auto モードでのバグがあります。 後に接続できない場合は[に出力するための切り替えやリレー モード](reference/connectivity.md#changing-the-connection-mode)、ください[バグを発生させる](https://aka.ms/vsls-problem)します。 |
| すべて | <strong>ダイレクト モード</strong>、サインインしますが、表示することが、<strong>タイムアウトまたは接続エラー</strong>または共有のいずれかに参加するときにします。 | ゲストとホストが直接接続できません。 お試しください[モードを自動またはリレー](reference/connectivity.md#changing-the-connection-mode)に、問題が解決したかどうかを参照してください。 必要があります[が個人のファイアウォールを手動で Live Share を許可する](reference/connectivity.md#manually-adding-a-firewall-entry)または単に中継モードを使用します。 |
| すべて | <strong>リレー モード</strong>は、サインインすることが通知されます、<strong>タイムアウトまたは接続エラー</strong>または共有のいずれかに参加するときにします。 | アクセス *. servicebus.windows.net にポート 80/443 がブロックされている、個人または会社のファイアウォールによってブロックされます。 お試しください[ダイレクト モード](reference/connectivity.md#changing-the-connection-mode)します。 |

参照してください、 [Live Share の接続要件](reference/connectivity.md)接続要件の詳細については、記事。

## <a name="see-also"></a>関連項目

クイックスタート

- [最初のプロジェクトを共有する](quickstart/share.md)
- [最初のセッションに参加する](quickstart/join.md)

方法

- [Visual Studio Code を使用して共同作業する](use/vscode.md)
- [Visual Studio を使用して共同作業する](use/vs.md)

参照

- [すべての主要なバグ、機能要求、および制限事項](https://aka.ms/vsls-issues)
- [すべての機能要求や制限事項](https://aka.ms/vsls-feature-requests)
- [Live Share の接続要件](reference/connectivity.md)
- [Linux インストールの詳細](reference/linux.md)
- [言語とプラットフォームのサポート](reference/platform-support.md)
- [拡張機能のサポート](reference/extensions.md)

それでも問題が解決しますか。 できます[フィードバック](support.md)します。
