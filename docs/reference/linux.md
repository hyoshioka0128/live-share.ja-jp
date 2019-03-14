---
title: Linux のインストールの詳細 - Visual Studio Live Share |Microsoft Docs
description: Linux 上の Visual Studio Live Share をインストールする方法の詳細情報。
ms.custom: ''
ms.date: 10/6/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 013eb234e5acca02a39e90f0697a146039bb2a89
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255928"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Linux のインストールの詳細

Linux は変化の激しい環境であり、膨大な数のデスクトップ環境とディストリビューションを動作させる複雑になることができます。 サポートされているバージョンを引き続き使用する場合**Ubuntu Desktop** (16.04 以上)、 **CentOS 7**、または**Fedora ワークステーション**(27 以上) のみを使用して**VS の公式のディストリビューションコード**、簡単にプロセスを検索する必要があります。 ただし、非標準構成またはダウン ストリームの配布を使用していることは可能性がありますか、いくつかの時差は発生しない可能性があります。 このドキュメントは、要件にいくつかの情報を提供します参考にしてトラブルシューティングの詳細をいくつかを取得および実行する構成が唯一のコミュニティである場合でもサポートされていません。 Live Share のみがサポートされます。 注**64 ビット Linux**します。

## <a name="install-linux-prerequisites"></a>Linux の前提条件をインストールします。

Linux のディストリビューションによっては、Live Share が動作するためのライブラリではありません。 既定では、Live Share は、検出し、Linux の前提条件をインストールしようとします。 Live Share 不足しているライブラリがそれらをインストールするためのアクセス許可を求めるから発生することのある問題を検出すると、トースト通知を確認します。

![Linux の前提条件が欠落しているトースト通知が表示されたメッセージ](../media/vscode-linux-prereq-missing.png)

[インストール] をクリックすると、OS が確認入力は、管理者/ルート (sudo) パスワードを続行することで、ターミナル ウィンドウが表示されます。 スクリプトが正常に完了すると仮定すると、再読み込みするを確認するメッセージが表示されたら、Visual Studio Code は、すべての設定にする必要があります! チェック アウトすることも**[ディストリビューションによってヒント](#tips-by-distribution)** の他のヒントと回避策が存在する場合。

スクリプトがお使いのディストリビューションをサポートしていないことを示すメッセージが表示される場合を参照してください**[コミュニティのサポートのディストリビューションに関するヒント](#tips-for-unsupported-distros)** については、コミュニティが私たちと共有します。

場合する**な VS Code のコマンドを実行するを望まない**を再実行するこのスクリプトの最新バージョン、いつでも手動でターミナル ウィンドウで次のコマンドを使用することもできます。

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>配布でのヒント

前提条件のインストール中には、上記のスクリプトは、さまざまなディストリビューションをについて説明しますと思うかもしれませんバニラ インストールから通常に不足しています。 次に、新規インストールされた、特定のディストリビューションで不足している主要なライブラリを示します。 一覧には、問題が発生した場合に役立つヒントをいくつか取得し、実行も提供します。

| 配布 | バニラが不足しているライブラリをインストールします。 | 追加の手順 |
|--------|-------------------|----|
| Ubuntu Desktop 18.04 (64 ビット) | &lt;none&gt;  | &lt;none&gt; |
| Ubuntu Desktop 16.04 (64 ビット) | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18.04 (64 ビット) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16.04 (64 ビット) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18.04 (64 ビット) |&lt;none&gt;  | <ul><li>確認"起動 GNOME サービスの起動時に"が"セッションと Startup"の"詳細設定 タブにチェックします。</li><li>サインインに問題を実行する場合は、インストール`seahorse`、「パスワードとキー」を開始、"Login"キーリングがあるロックを解除できることを確認します。</li></ul> |
| Xubuntu 16.04 (64 ビット) | &lt;none&gt; | <ul><li>確認"起動 GNOME サービスの起動時に"が"セッションと Startup"の"詳細設定 タブにチェックします。</li><li>サインインに問題を実行する場合は、インストール`seahorse`、「パスワードとキー」を開始、"Login"キーリングがあるロックを解除できることを確認します。</li></ul> |
| Mint 19 シナモン (64 ビット) | &lt;none&gt;  | &lt;none&gt; |
| Mint 18.3 シナモン (64 ビット) | &lt;none&gt;  | &lt;none&gt; |
| Debian 10 (マウント) (64 ビット) のテスト | 不明なため、安定性は、リリースされません。 | <ul><li>Debian のテストと可能性あり (Sid) が正式にサポートされていません。</li><li>[既知の問題](https://github.com/dotnet/corefx/issues/33179)Live Share に影響する .NET Core でします。 </li><li>参照してください[回避策についてはここで](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249)します。</li></ul> |
| Debian 9 への GNOME デスクトップ (64 ビット) | &lt;none&gt; | <ul><li>インストールする必要があります`sudo`自動インストール スクリプトを使用して sudo グループにユーザーを追加します。</li>  |
| Fedora ワークステーション 29 (64 ビット) | `openssl-compat10` | &lt;none&gt; |
| Fedora ワークステーション 28 (64 ビット) | &lt;none&gt; | &lt;none&gt; |
| Fedora ワークステーション 27 (64 ビット) | &lt;none&gt; | &lt;none&gt; |
| CentOS 7 への GNOME デスクトップ (64 ビット) | &lt;none&gt; | &lt;none&gt; |

参照してください**[コミュニティのサポートのディストリビューションに関するヒント](#tips-for-community-supported-distros)** Debian 以外の他の方法については Ubuntu または全文ベースのディストリビューション/。

追加の詳細についても確認できます[下](#detailed-library-requirements)Live Share 必要がある特定のライブラリにします。

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>コミュニティのヒントには、ディストリビューションがサポートされています

外部、Debian ディストリビューション Ubuntu または全文ツリーが正式に Visual Studio Code または .NET Core でサポートされていません。 そのため、拡張機能によっては正式にサポートされていませんで Visual Studio Live Share か。 ただし、コミュニティでは、Live Share を起動して実行の他のディストリビューションの数に関する有用な情報の貢献します。

> **プル要求の開始:** お気に入りの分布を使用してこの情報を更新する場合のプル要求を送信[ファイル](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md)docs GitHub リポジトリにします。 さらに、お気に入りの配布をサポートしている依存関係のインストーラーを取得したい場合は、PR を送信できます[このファイルの](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh)します。

| 配布 | 作業しますか。 | バニラが不足しているライブラリをインストールします。 | 追加の手順 |
|--------------|----------|-------------------|------------------|
| Arch Linux (64 ビット) | はい | によって異なります。 可能なライブラリ: `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>サポートされている、[前提条件のインストール スクリプト](#install-linux-prerequisites)します。</li><li>使用して、 [visual studio コード bin](https://aur.archlinux.org/packages/visual-studio-code-bin) for VS Code AUR のパッケージ。</li><li>`sudo` する必要がありますを使用するには、自動化された前提条件のインストール スクリプト。</li><li>`gnome-keyring` その他必要があります[セットアップ手順](https://wiki.archlinux.org/index.php/GNOME/Keyring)一部のデスクトップ環境でします。</ul> |
| Manjaro 17.1 (64 ビット) | [はい] | `xorg-xprop liburcu` | <ul><li>サポートされている、[前提条件のインストール スクリプト](#install-linux-prerequisites)します。</li><li>使用して、 [visual studio コード bin](https://aur.archlinux.org/packages/visual-studio-code-bin) for VS Code AUR のパッケージ。</li></ul> |
| openSuSE LEAP 15 KDE (64 ビット) | [はい] | `libopenssl1_0_0 gnome-keyring` | <ul><li>前提条件のインストール スクリプトによってサポートされています。</li></ul> |
| Solus 3 (64 ビット) | [はい] | `xprop` | <ul><li>サポートされている、[前提条件のインストール スクリプト](#install-linux-prerequisites)します。</li><li>バージョン、 `vscode` 57 をリリースする前にパッケージには、必要な product.json 値が不足しているが ([後述](#vs-code-oss-issues))。 アップグレード、`vscode`この問題を解決するのにはパッケージです。</li></ul> |
| Gentoo (64 ビット) | [はい] | 大幅に変わります。 考えられる不足しているパッケージ: `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>`visual-studio-code`にパッケージ化、 **jorgicio**オーバーレイが動作しています。</li></ul>

## <a name="install-prerequisites-manually"></a>前提条件を手動でインストールします。

 Live Share を使用することをお勧めします中に**依存関係のインストール スクリプト**、このセクションではさらに詳細に必要なライブラリする自分でこれらの手順を実行するか、でサポートされていない配布を使用している場合に、。スクリプトです。

バニラ インストールでの一般的な不足しているライブラリが記載されて、[ディストリビューションによってヒント](#tips-by-distribution)と[コミュニティのサポートのディストリビューションに関するヒント](#tips-for-unsupported-distros)セクション。

### <a name="detailed-library-requirements"></a>詳細なライブラリの要件

Visual Studio Live Share のネイティブ ライブラリの要件は、資格情報、およびブラウザーの統合を保持する .NET Core 2.1 では、libsecret の使用から取得されます。 次の表は、.NET Core で正式にサポートされているディストリビューションのこれらの要件をまとめたものです。

| 配布 | .NET core の要件 | 資格情報の記憶域の要件| ブラウザーの統合の要件 |
|--------------|-----------|--------------------|------------|
| Ubuntu およびダウン ストリームのディストリビューション | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (Ubuntu 16.04、ミント 18.3) または`libicu57`(Ubuntu 17.10) 用または`libicu60`(Ubuntu 18.04、ミント 19) | `libsecret-1-0 gnome-keyring` (または libsecret にキーリングがサポートされています - Kwallet は libsecret をサポートしていません) | `desktop-file-utils x11-utils` |
| Debian 9 およびダウン ストリームのディストリビューション | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (または libsecret にキーリングがサポートされています - Kwallet は libsecret をサポートしていません) | `desktop-file-utils x11-utils` |
| 全文/CentOS/Fedora | `openssl-libs krb5-libs zlib libicu` Fedora も必要です。 `compat-openssl10`| `libsecret gnome-keyring` (または libsecret にキーリングがサポートされています - Kwallet は libsecret をサポートしていません) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (または libsecret にキーリングがサポートされています - Kwallet は libsecret をサポートしていません) | `desktop-file-utils xprop`

他のディストリビューションには、同じライブラリが必要ですが、そのパッケージ名が異なる場合があります。 これらのいくつかを見つけることができます、[コミュニティのサポートのディストリビューションに関するヒント](#tips-for-unsupported-distros)セクション。

### <a name="debian--ubuntu"></a>Debian / Ubuntu

実行して Debian/Ubuntu ベースのディストリビューションでライブラリをインストールすることがあります`sudo apt install <library-name>`ターミナルでします。

Ubuntu ベースのディストリビューションが Mint など、次のコマンドを実行します。

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Debian 9 とダウン ストリームのディストリビューションの Ubuntu 以外の場合は、次のコマンドを実行します。

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora/CentOS/全文

実行して全文 CentOS/Fedora/ベースのディストリビューションでライブラリをインストールすることがあります`sudo yum install <library-name>`ターミナルでします。 たとえば、すべてのものをインストールこれされます。

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>VS OSS のコードの問題

> **Arch Linux/Manjaro ユーザー:** 使用して、 [visual studio-ビン](https://aur.archlinux.org/packages/visual-studio-code-bin)AUR のパッケージにこの問題を回避します。

かバニラまたは VS コードの OS のバージョンが変更される Visual Studio Code のパッケージにで重要な値は不足している`product.json`ファイルを Visual Studio Live Share をアクティブ化することを防ぎます。

この問題を達した可能性がありますを表示する簡単な方法がヘルプを参照して、>"トグル Developer Tools"と Live Share の拡張機能を示すスタック トレースを検索する場合の参照をライセンス認証しなかった"提案 API"を使用していたため

これは、問題を確認するには、内容を確認`product.json`します。 ファイルの場所は、パッケージによって異なりますが、これは、通常、次の場所のいずれかの。

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

場合、`extensionAllowedProposedApi`プロパティが不足している、または"ms-vsliveshare.vsliveshare"参照が表示されない、この問題を OS バージョンを使用しています。

として、**回避策**、product.json に、次を追加することができます。

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

参照してください[上](#tips-for-community-supported-distros)を使用する配布が正常に機能するかどうかの詳細についてはします。

## <a name="linux-browser-integration"></a>Linux のブラウザーの統合

Visual Studio Live 共有通常**追加のインストール手順は必要ありません**Linux 上のブラウザーの統合を有効にします。

これを実現する Live Share 自動的にデスクトップのファイルが配置で`~/.local/share/applications`と必要なランチャー自体で`~/.local/share/vsliveshare`拡張機能が最初に初期化します。 コンソール アプリケーションは、これが成功した場合に、アクションは必要ありません。

場合によっては、ディストリビューションかサポートしていないこの場所または取得、バニラのインストールと連動するように調整が必要です。 このような場合は、Live Share にフォールバックを使用して`/usr/local/share`代わりにします。 その結果、 **admin (sudo) パスワードが必要である通知されます**インストール プロセスを完了します。 ブラウザー起動ツールをインストールすることを示す、ターミナル ウィンドウが表示されます。 単に入力を求められたら、パスワードを入力し、ターミナル ウィンドウを閉じる、インストールが完了したら enter キーを押します。

コマンドは、自分で代わりに実行する場合は、「コピー代わりに」ターミナル コマンドを代わりに、クリップボードにコピーするをクリックすることができます。

最後に、この手順を完全にスキップする場合、することもできます[コラボレーション セッションを手動で結合](../use/vscode.md#join-manually)が招待のリンクをブラウザーで開くと、参加させることはできません。 アクセスできること常にコマンドは、後でもう一度を押して注**Ctrl + Shift + P/Cmd + Shift + P**を選択して、"ライブ共有。「ランチャー セットアップ コマンド。

## <a name="see-also"></a>関連項目

- [方法:Visual Studio Code を使用して共同作業します。](../use/vscode.md)
- [Live Share の接続要件](connectivity.md)
- [Live Share のセキュリティ機能](security.md)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
