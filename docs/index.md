---
title: 概要 - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share とその機能の概要です。
ms.custom: null
ms.date: 04/26/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
  - liveshare
---

<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>Visual Studio Live Share とは

> **注:現在、Visual Studio Live Share はプレビュー段階です。ユーザー エクスペリエンスと機能は最終版ではありません。**

Visual Studio Live Share へようこそ。 Live Share を使うと、使っているプログラミング言語や構築しているアプリの種類に関係なく、リアルタイムで他のユーザーと共同で編集したりデバッグしたりできます。 これにより、現在のプロジェクトを瞬時に安全に共有してから、必要に応じて、デバッグ セッション、ターミナルのインスタンス、localhost の Web アプリ、音声通話などを共有することができます。

さらに、従来のペア プログラミングとは異なり、開発者は Visual Studio Live Share を使って、各自の好みのエディター設定 (テーマ、キー バインドなど) を維持し、独自のカーソルを持ちながら連携することができます。 これにより、次から次へとシームレスに移行し、独自にアイデアやタスクを調べることができます。 実際には、共同で "_かつ_" 独自に作業を行うこの機能により、一般的なユース ケースの多くに対して潜在的により自然なコラボレーション エクスペリエンスが提供されます。

開始する準備はできましたか。 この記事では、いくつかの概念と必要な拡張機能のインストール方法について説明します。 簡略化されたバージョンをお探しの場合は、[共有](quickstart/share.md)と[参加](quickstart/join.md)に関するクイック スタートをご覧ください。

> [!TIP]
> "*独自のコラボレーション セッションに参加*" できることをご存知でしたか。 これを使うと、Live Share を独自に試したり、Visual Studio または VS Code のインスタンスを起動してリモートでそれに接続したりできます。 両方のインスタンスで同じ ID を使用することもできます。 ぜひお試しください。

## <a name="install-visual-studio-live-share"></a>Visual Studio Live Share をインストールする

開始する前に、Live Share のコア要件を満たす Visual Studio または Visual Studio Code のバージョンがインストールされていることを確認する必要があります。

- **Visual Studio Code 1.22.0 以上** - Windows 7、8.1、または 10、macOS "*(Sierra 10.12 以上のみ)*"、64 ビット Linux "*(64 ビット Ubuntu Desktop 16.04 以上、Fedora 27 以上が推奨されます - [詳細情報](use/vscode.md#installation))*"。
- **Visual Studio 2017 15.6 以上** (任意のエディション) - Windows 7、8.1、または 10。
- **Visual Studio 2019** (任意のエディション) - Windows 7、8.1、または 10。

その後は、Visual Studio Live Share 拡張機能を簡単にダウンロードしてインストールできます。

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0+)</strong><br />
        1. Windows (7、8.1、または 10)、macOS <b>(Sierra+)</b>、64 ビット Linux <b>(<a href="use/vscode.md#installation">詳細</a>)</b> 用の <a href="https://code.visualstudio.com/">Visual Studio Code</a> をインストールします<br />
        2. マーケットプレースから Visual Studio Live Share 拡張機能をダウンロードしてインストールします。 <br />
        3. 再度読み込み、依存関係がダウンロードおよびインストールされるまで待機します (ステータス バーを参照)。<br />
        4. <strong>Linux</strong>:<a href="reference/linux.md#install-linux-prerequisites">ライブラリのインストール</a>を求められた場合は、インストールをクリックし、パスワードを入力して、完了したら VS Code を再起動します。<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide.svg" width="128px" alt="Visual Studio logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 以上</strong><br />
        1. 最新バージョンの <a href="https://visualstudio.microsoft.com/vs/">Visual Studio 2017</a> (15.6+) を Windows (7、8.1、または 10) にインストールします。<br/>
        2. <a href="reference/platform-support.md">サポートされているワークロード</a>をインストールします。 (例: ASP.NET、.NET Core、C++、Node.js)<br />
        3. マーケットプレースから Visual Studio Live Share 拡張機能をダウンロードしてインストールします。 <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-preview.svg" width="128px" alt="Visual Studio Preview logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. 最新のプレビュー バージョンの <a href="https://aka.ms/vs-preview">Visual Studio 2019</a> をインストールします。<br/>
        2. <a href="reference/platform-support.md">サポートされているワークロード</a>をインストールします。 (例: ASP.NET、.NET Core、C++、Node.js)<br />
        3. Visual Studio Live Share は、既定でこれらのワークロードと共にインストールされます。 <br />
    </td>
</tr>
</table>

Visual Studio Live Share をダウンロードして使用すると、[ライセンス条項](https://aka.ms/vsls-license)と[プライバシーに関する声明](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)に同意したものと見なされます。 問題が発生した場合は、[トラブルシューティング](troubleshooting.md)に関するページをご覧ください。

必要な作業は以上です。 これで、VS Code の左下にサインイン状態のバーが、Visual Studio の右上に共有ボタンが表示されるようになりました。 次の作業については、ドキュメントの残りの部分をご覧ください。

## <a name="concepts-and-features"></a>概念と機能

あらゆる製品と同様に、Visual Studio Live Share にはいくつかの中心的な概念から構築された一連の強力な機能が用意されています。 このセクションでは、いくつかの概念と機能の概要について説明します。

### <a name="collaboration-sessions"></a>コラボレーション セッション

Visual Studio Live Share 内のすべてのコラボレーション アクティビティは、1 人の**コラボレーション セッション ホスト**と 1 人以上の**ゲスト**を伴います。 ホストはコラボレーション セッションを開始した人であり、参加する人はすべてゲストです。

コラボレーション セッション ホストはすべてのツールとサービスを使用できますが、ゲストがアクセスできるのは、ホストが共有している特定のもののみです。 これには、コード、サーバーの実行、デバッグ セッション、ターミナルなどが含まれます。 現在、共有されるすべてのコンテンツはホストのマシン上に保持され、クラウドやゲストのマシンとは同期されません。これにより、"_簡単なアクセス_" と "_セキュリティの向上_" が実現されます。 その利点は、ゲストが参加した瞬間にソリューション全体が利用可能になること、またホストがコラボレーション セッションを終了した瞬間にコンテンツを利用できなくなることです。 さらに、ゲストのパフォーマンス向上のために IDE やエディターにより作成された一時ファイルは、セッション終了時に自動的にクリーンアップされます。

#### <a name="sharing"></a>共有

ホストとして "共有" する場合、プロジェクト、ソリューション、またはフォルダーの内容を共有するコラボレーション セッションを開始します。 ゲストは、ご自身が送信する招待リンクを使ってこのコンテンツへのアクセスを取得します。 "共有" は "プロジェクトを共有" の短縮形ですが、デバッグのような他の機能を共有するためにも使用されます。

**詳細情報:**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-project) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-project)

#### <a name="joining"></a>結合

ホストから送信された招待リンクをクリックすると、ゲストとしてコラボレーション セッションに "参加" することができ、ホストが共有することを選択したすべてのコンテンツや機能にアクセスできます。 Web リンクにより、既に拡張機能をインストールしている場合はコラボレーション セッションを始めるための簡単な方法が、それ以外の場合は情報を設定するための簡単な方法が提供されます。

**詳細情報:**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#join-a-collaboration-session) [![VS](media/vs-icon-15x15.png)](use/vs.md#join-a-collaboration-session)

### <a name="features"></a>フィーチャー

#### <a name="co-editing"></a>共同編集

別のコラボレーターと同じファイルを開くと、すぐにそのファイルの内容を "共同編集" することができます。 各コラボレーターの編集内容や、各自のカーソルと選択などを確認できます。 さらに優れた点は、同じファイルの編集を常に強制されるわけではないため、自分の好きなように共同作業したり、単独で作業したりできるということです。

> [!NOTE]
> 共同編集にはいくつかの制限事項があります。 言語ごとの機能の状態については、[プラットフォームのサポート](reference/platform-support.md)に関するページをご覧ください。

**詳細情報:**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-editing) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-editing)

#### <a name="following-and-focusing"></a>フォローとフォーカス

複数のファイルやコード内の場所にまたがる問題や設計について説明する必要がある場合があります。 このような状況では、共同編集するときに、プロジェクト全体を移動する同僚を一時的にフォローすると便利な場合があります。 このため、ゲストは、コラボレーション セッションに参加するとホストの編集場所を自動的に "フォロー" します。 ホストとゲストは、簡単なマウス クリックでお互いのフォローを開始および終了できます。 さらに、すべての参加者に対して自分をフォローするよう求めたい場合があります。 Live Share では、フォローが返しやすくなる通知を使って、全員が自分に注意を "フォーカス" するよう要求することができます。

**詳細情報:**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#following) [![VS](media/vs-icon-15x15.png)](use/vs.md#following)

#### <a name="co-debugging"></a>共同デバッグ

厄介なコーディングの問題やバグをデバッグしているときに、それを見る人が増えると非常に役立ちます。 ホストである場合、Live Share により、すべてのゲストとデバッグ セッションを共有することで "共同デバッグ" が自動的に有効になります。 手順を実行しながら独自に調査する機能と共に、共同編集する機能がそれぞれに与えられます。

> [!NOTE]
> 言語またはプラットフォームごとのデバッグ機能の状態については、[プラットフォームのサポート](reference/platform-support.md)に関するページをご覧ください。

**詳細情報:**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-debugging) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-debugging)

#### <a name="share-server--share-port"></a>サーバーの共有 / ポートの共有

共同デバッグを行うとき、デバッグ セッション用にホストが提供するアプリケーションのさまざまな部分にアクセスできると非常に便利です。 ブラウザーでアプリにアクセスしたり、ローカル データベースにアクセスしたり、またはツールから REST エンドポイントを指定したりしたい場合があります。 Live Share では "サーバーを共有" することができます。これにより、ホストのマシン上のローカル ポートが、各ゲストのマシン上のまったく同じポートにマップされます。 次にゲストは、そのアプリケーションが自分のマシン上でローカルに実行されている場合とまったく同じように、それとやり取りすることができます (たとえば、ホストとゲストの両方が、次で実行される Web アプリにアクセスできます: http://localhost:3000)。

**詳細情報:**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-server) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-server)

#### <a name="share-terminals"></a>ターミナルの共有

最新の開発では、さまざまなコマンド ライン ツールを頻繁に使用します。 ありがたいことに、Live Share を使うとホストは必要に応じてゲストと "ターミナルを共有" することができます。 共有されたターミナルは、読み取り専用または完全な共同作業用にすることができます。このため、ホストとゲストの両方がコマンドの実行と結果の確認を行うことができます。 ホストは、他のコラボレーターが各自でコマンドを実行できるのか、またはただコマンドの出力を確認できるだけなのかどうかを、いつでも管理し、決定することができます。 実際、自分だけが確認したい操作は、すべて非共有のターミナルで実行できます。

**詳細情報:**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-terminal) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-terminal)

#### <a name="access-controls"></a>アクセスの制御

Visual Studio Live Share では、共同作業のための優れた方法が参加者に多数提供されます。 しかし、ホストと対話するためにゲストに与えられるオプションの数や柔軟性を使って、参加するゲストを明示的に承認したり、特定のファイルやフォルダーへのアクセスをロックダウンしたりしたい場合があります。 Live Share には、読み取り専用やゲストの受け入れ要求など、役に立つさまざまな設定があります。

**詳細情報:**[![VS Code](media/vscode-icon-15x15.png)](reference/security.md) [![VS](media/vs-icon-15x15.png)](reference/security.md)

#### <a name="flexible-connection-modes"></a>柔軟な接続モード

最適なパフォーマンスを実現するために、Visual Studio Live Share では 2 つの主要な "接続モード": "直接" と "リレー" がサポートされています。 直接モードでは、ゲストは Web を経由せず直接ホストに接続します。 リレー モードを使うと、完全に別のネットワーク内にいるゲストが、インターネット リレーを経由してホストに接続できます。 すべての場合で、送受信される情報にコラボレーターのみがアクセスできるように、接続は SSH または SSL で暗号化されます。 既定では、Live Share は "自動" モードであり、最初に直接接続を試行してからリレーにフェールオーバーしますが、必要に応じて 1 つのモードにロックすることができます。

**詳細情報:**[![VS Code](media/vscode-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode) [![VS](media/vs-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode)

## <a name="see-also"></a>関連項目

クイックスタート

- [最初のプロジェクトを共有する](quickstart/share.md)
- [最初のセッションに参加する](quickstart/join.md)

方法

- [Visual Studio Code を使用して共同作業する](use/vscode.md)
- [Visual Studio を使用して共同作業する](use/vs.md)

関連項目

- [Live Share の接続要件](reference/connectivity.md)
- [Live Share のセキュリティ機能](reference/security.md)
- [言語とプラットフォームのサポート](reference/platform-support.md)
- [拡張機能のサポート](reference/extensions.md)
- [リリース ノート](https://aka.ms/vsls-releases)

問題が発生していますか? [トラブルシューティング](troubleshooting.md)または[フィードバックの送信](support.md)に関するページをご覧ください。
