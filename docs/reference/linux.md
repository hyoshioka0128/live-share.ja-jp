---
title: Linux インストールの詳細-Visual Studio Live Share |Microsoft Docs
description: Linux での Visual Studio Live Share のインストールの詳細については、こちらを参照してください。
ms.custom: ''
ms.date: 10/6/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 69bc178ebb4052757f984d67482d216335f46dac
ms.sourcegitcommit: 5180aab73c086cbded6aae01aa01f71fb991dee1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818077"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Linux のインストールの詳細

Linux は変化の激しい環境であり、膨大な数のデスクトップ環境やディストリビューションがあるため、作業が複雑になる可能性があります。 サポートされているバージョンの**Ubuntu Desktop** (16.04 +)、 **centos 7**、または**Fedora Workstation** (27 +) を使用していて、 **VS Code の公式ディストリビューション**のみを使用している場合は、そのプロセスをすぐに確認する必要があります。 ただし、標準ではない構成またはダウンストリーム ディストリビューションを使用する場合は、問題が発生する可能性があります。 このドキュメントでは、構成がコミュニティのみでサポートされている場合でも、これらの要件とトラブルシューティングの詳細について説明します。 Live Share でサポートされているのは**64 ビット Linux**のみであることに注意してください。

## <a name="install-linux-prerequisites"></a>Linux の前提条件をインストールする

Linux のディストリビューションによっては、Live Share が機能するために必要なライブラリがありません。 既定では、Live Share は自動で Linux の前提条件を検出してインストールしようとします。 Live Share でライブラリの不足が原因の可能性がある問題が発生すると、それらをインストールする許可を求めるトースト通知が表示されます。

![Linux の前提条件が不足していることを示すメッセージを示すトースト通知](../media/vscode-linux-prereq-missing.png)

[インストール] をクリックすると、ターミナルウィンドウが表示されます。 OS は、管理者/ルート (sudo) パスワードを入力して続行するように要求します。 スクリプトが正常に完了した場合は、メッセージが表示されたら Visual Studio Code 再読み込みします。すべて設定する必要があります。 他のヒントや回避策については、 **[ディストリビューション別のヒント](#tips-by-distribution)** を確認することもお勧めします。

スクリプトがディストリビューションをサポートしていないことを示すメッセージが表示される場合は、 **[コミュニティがサポートするディストリビューションのヒント](#tips-for-unsupported-distros)** を参照してください。コミュニティが Microsoft と共有している情報が見つかります。

コマンドを**VS Code 実行しない**場合は、ターミナルウィンドウで次のコマンドを使用して、このスクリプトの最新バージョンをいつでも手動で再実行することもできます。

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>配布によるヒント

上記の前提条件インストールスクリプトではさまざまなディストリビューションが使用されていますが、通常、バニラのインストールにはどのようなものが不足していますか。 次の一覧は、指定された配布の新規インストールで見つからなかった主なライブラリを示しています。 また、この一覧には、問題が発生した場合に起動して実行するのに役立つヒントもいくつか用意されています。

| 配布 | バニラ不足ライブラリのインストール | 追加の手順 |
|--------|-------------------|----|
| Ubuntu Desktop 18.04 (64 ビット) | &lt;none&gt;  | &lt;none&gt; |
| Ubuntu Desktop 16.04 (64 ビット) | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18.04 (64 ビット) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16.04 (64 ビット) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18.04 (64 ビット) |&lt;none&gt;  | <ul><li>[セッションとスタートアップ] の [詳細設定] タブで、[スタートアップ時に GNOME サービスを起動する] チェックボックスがオンになっていることを確認します。</li><li>サインインの問題が発生した場合は、`seahorse`をインストールし、"パスワードとキー" を起動して、"ログイン" が実行されていることと、ロックを解除できることを確認します。</li></ul> |
| Xubuntu 16.04 (64 ビット) | &lt;none&gt; | <ul><li>[セッションとスタートアップ] の [詳細設定] タブで、[スタートアップ時に GNOME サービスを起動する] チェックボックスがオンになっていることを確認します。</li><li>サインインの問題が発生した場合は、`seahorse`をインストールし、"パスワードとキー" を起動して、"ログイン" が実行されていることと、ロックを解除できることを確認します。</li></ul> |
| Mint 19 シナモン (64 ビット) | &lt;none&gt;  | &lt;none&gt; |
| Mint 18.3 シナモン (64 ビット) | &lt;none&gt;  | &lt;none&gt; |
| Debian 10 (Buster) のテスト (64 ビット) | リリースが安定していません。不明です。 | <ul><li>Debian テストと不安定 (Sid) は公式にはサポートされていません。</li><li>.NET Core には Live Share に影響する[既知の問題](https://github.com/dotnet/corefx/issues/33179)があります。 </li><li>[回避策については、こちらを](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249)参照してください。</li></ul> |
| Debian 9 GNOME デスクトップ (64 ビット) | &lt;none&gt; | <ul><li>自動インストールスクリプトを使用するには、`sudo` をインストールし、sudo グループにユーザーを追加することが必要になる場合があります。</li>  |
| Fedora ワークステーション 29 (64 ビット) | `openssl-compat10` | &lt;none&gt; |
| Fedora ワークステーション 28 (64 ビット) | &lt;none&gt; | &lt;none&gt; |
| Fedora ワークステーション 27 (64 ビット) | &lt;none&gt; | &lt;none&gt; |
| CentOS 7 GNOME デスクトップ (64 ビット) | &lt;none&gt; | &lt;none&gt; |

参照してください **[コミュニティのサポートのディストリビューションに関するヒント](#tips-for-community-supported-distros)** Debian 以外の他の方法については Ubuntu または全文ベースのディストリビューション/。

その他の詳細については、Live Share 必要な特定のライブラリ[を参照してください。](#detailed-library-requirements)

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>コミュニティでサポートされているディストリビューションのヒント

Debian/Ubuntu または RHL ツリーの外部にあるディストリビューションは、Visual Studio Code または .NET Core で公式にサポートされていません。 したがって、拡張機能によって、Visual Studio Live Share によって正式にサポートされることはありません。 しかし、このコミュニティでは、多くの追加のディストリビューションで Live Share の取得と実行に関する有益な情報が提供されています。

> **Pr ようこそ:** お気に入りの配布でこの情報を更新することに関心がある場合は、[このファイル](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md)の PR を docs GitHub リポジトリに送信してください。 さらに、お気に入りの配布をサポートする依存関係のインストーラーを取得したい場合は、[このファイルの](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh)PR を送信できます。

| 配布 | 時? | バニラ不足ライブラリのインストール | 追加の手順 |
|--------------|----------|-------------------|------------------|
| アーキテクチャ Linux (64 ビット) | ○ | て. 使用可能なライブラリ: `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>[前提条件のインストールスクリプト](#install-linux-prerequisites)によってサポートされます。</li><li>VS Code には、 [visual studio](https://aur.archlinux.org/packages/visual-studio-code-bin)の AUR パッケージを使用します。</li><li>必須コンポーネントの自動インストールスクリプトを使用するには、`sudo` をインストールする必要があります。</li><li>`gnome-keyring` には、デスクトップ環境によっては、追加の[セットアップ手順](https://wiki.archlinux.org/index.php/GNOME/Keyring)が必要になる場合があります。</ul> |
| Manjaro 17.1 (64 ビット) | ○ | `xorg-xprop liburcu` | <ul><li>[前提条件のインストールスクリプト](#install-linux-prerequisites)によってサポートされます。</li><li>VS Code には、 [visual studio](https://aur.archlinux.org/packages/visual-studio-code-bin)の AUR パッケージを使用します。</li></ul> |
| openSuSE LEAP 15 KDE (64 ビット) | ○ | `libopenssl1_0_0 gnome-keyring` | <ul><li>前提条件のインストールスクリプトによってサポートされます。</li></ul> |
| この 3 (64 ビット) | ○ | `xprop` | <ul><li>[前提条件のインストールスクリプト](#install-linux-prerequisites)によってサポートされます。</li><li>リリース57より前の `vscode` パッケージのバージョンには、必要な製品の json 値 ([下記参照](#vs-code-oss-issues)) がありませんでした。 この問題を解決するには、`vscode` パッケージをアップグレードしてください。</li></ul> |
| Gentoo (64 ビット) | ○ | 高度な変数。 パッケージが見つからない可能性があります: `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>**Jorgicio**オーバーレイの `visual-studio-code` パッケージが機能することがわかっています。</li></ul>

## <a name="install-prerequisites-manually"></a>前提条件を手動でインストールする

 Live Share の**依存関係インストールスクリプト**を使用することをお勧めしますが、このセクションでは、これらの手順を自分で実行する場合や、スクリプトでサポートされていないディストリビューションを使用する場合のライブラリ要件について詳しく説明します。

バニラのインストールで一般的に見つからないライブラリについては、「[配布に関するヒント](#tips-by-distribution)」と「[コミュニティでサポートされているディストリビューションのヒント](#tips-for-unsupported-distros)」セクションを参照してください。

### <a name="detailed-library-requirements"></a>ライブラリの詳細要件

Visual Studio Live Share のネイティブライブラリの要件は、.NET Core 2.1、libsecret-1.so.0 を使用して資格情報を保持すること、およびブラウザーの統合に起因します。 次の表は、.NET Core で正式にサポートされているディストリビューションの要件をまとめたものです。

| 配布 | .NET Core の要件 | 資格情報ストレージの要件| ブラウザー統合の要件 |
|--------------|-----------|--------------------|------------|
| Ubuntu および下流のディストリビューション | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (Ubuntu 16.04、Mint 18.3 の場合) または `libicu57` (ubuntu 17.10 の場合) または `libicu60` (Ubuntu 18.04 の場合は Mint 19) | `libsecret-1-0 gnome-keyring` (または libsecret-1.so.0 でサポートされているキーリング-Kwallet は libsecret-1.so.0 をサポートしていません) | `desktop-file-utils x11-utils` |
| Debian 9 および下流のディストリビューション | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (または libsecret-1.so.0 でサポートされているキーリング-Kwallet は libsecret-1.so.0 をサポートしていません) | `desktop-file-utils x11-utils` |
| RHL/CentOS/Fedora | `openssl-libs krb5-libs zlib libicu` Fedora にも `compat-openssl10` が必要です| `libsecret gnome-keyring` (または libsecret-1.so.0 でサポートされているキーリング-Kwallet は libsecret-1.so.0 をサポートしていません) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (または libsecret-1.so.0 でサポートされているキーリング-Kwallet は libsecret-1.so.0 をサポートしていません) | `desktop-file-utils xprop`

他のディストリビューションは同じライブラリを必要としますが、パッケージ名は異なる場合があります。 これらの詳細については、[コミュニティでサポートされているディストリビューションに](#tips-for-unsupported-distros)関するセクションを参照してください。

### <a name="debian--ubuntu"></a>Debian/Ubuntu

ターミナルで `sudo apt install <library-name>` を実行して、Debian/Ubuntu ベースのディストリビューションにライブラリをインストールすることができます。

Mint を含む Ubuntu ベースのディストリビューションの場合は、次のように実行します。

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Debian 9 および Ubuntu 以外のダウンストリームディストリビューションの場合は、次のように実行します。

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora/CentOS/RHL

ライブラリは、ターミナルで `sudo yum install <library-name>` を実行することで、Fedora/CentOS/RHL ベースのディストリビューションにインストールできます。 たとえば、次のようなすべてのものがインストールされます。

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>OSS の問題の VS Code

> **アーキテクチャ Linux/Manjaro ユーザー:** この問題を回避するには、 [visual studio bin](https://aur.archlinux.org/packages/visual-studio-code-bin) AUR パッケージを使用します。

VS Code OSS のバニラまたは変更されたバージョンである Visual Studio Code のパッケージでは `product.json` ファイルに重大な値がないため、Visual Studio Live Share をアクティブにできません。

この問題が発生していることをすばやく確認するには、[> の開発者ツール切り替え] にアクセスし、Live Share 拡張機能が "提示された API" を使用していたためにアクティブ化されなかったことを示すスタックトレースがあることを確認してください。

これが問題であることを確認するには、`product.json`の内容を確認します。 ファイルの場所はパッケージによって異なりますが、通常は次のいずれかの場所にあります。

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

`extensionAllowedProposedApi` プロパティが見つからないか、"vsliveshare" が参照されていない場合は、この問題のある OSS バージョンを使用しています。

この**回避策**として、次のものを製品. json に追加できます。

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

使用しているディストリビューションが動作することがわかっているかどうかの詳細については、[上記](#tips-for-community-supported-distros)を参照してください。

## <a name="linux-browser-integration"></a>Linux ブラウザーの統合

通常、Visual Studio Live Share では、Linux 上でブラウザーの統合を有効にするために**追加のインストール手順が必要ありません**。

これを実現するために、Live Share は、拡張機能が最初に初期化されるときに、`~/.local/share/applications` にデスクトップファイルを自動的に配置し、必要なランチャー自体を `~/.local/share/vsliveshare` します。 これが成功した場合、ユーザーの操作は必要ありません。

場合によっては、ディストリビューションがこの場所をサポートしていないか、またはバニラのインストールで動作するように調整が必要になることがあります。 このような場合は、代わりに `/usr/local/share` を使用するように Live Share します。 このため、インストールプロセスを完了するに**は、管理者 (sudo) パスワードが必要であることが通知される場合があり**ます。 ブラウザー ランチャーのインストール先を示すターミナル ウィンドウが表示されます。 入力を求められたらパスワードを入力し、インストールが完了したら Enter キーを押してターミナル ウィンドウを閉じます。

代わりにコマンドを実行する場合は、[代わりにコピーする] をクリックすると、ターミナルコマンドがクリップボードにコピーされます。

最後に、この手順を完全にスキップすることを選択した場合でも、[コラボレーションセッションを手動で参加](../use/vscode.md#join-manually)させることができますが、ブラウザーで招待リンクを開いて参加することはできません。 **Ctrl + shift + p/Cmd + Shift + p キー**を押して、"Live Share: ランチャー Setup" コマンドを選択することによって、後でいつでもコマンドにアクセスできることに注意してください。

## <a name="see-also"></a>関連項目

- [方法: Visual Studio Code を使用したコラボレーション](../use/vscode.md)
- [Live Share の接続要件](connectivity.md)
- [Live Share のセキュリティ機能](security.md)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
