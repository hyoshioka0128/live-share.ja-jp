---
title: 概要 - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share とその機能の概要です。
ms.custom: ''
ms.date: 10/30/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: fubaduba
ms.author: fubaduba
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 8091a7ba5cf1f57f192ecea18da4473c8fdd99f7
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73179951"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->
# <a name="live-share-features-and-concepts"></a>Live Share の機能と概念 

Live Share は、ユーザーのための強力な機能として機能する革新的なアーキテクチャと概念を使用して構築されています。 次に、Live Share の特徴と、コラボレーションスペースのリーダーになる機能をすべて紹介します。 

### <a name="collaboration-sessions"></a>コラボレーション セッション

Visual Studio Live Share 内のすべてのコラボレーション アクティビティは、1 人の**コラボレーション セッション ホスト**と 1 人以上の**ゲスト**を伴います。 ホストはコラボレーション セッションを開始した人であり、参加する人はすべてゲストです。

コラボレーション セッション ホストはすべてのツールとサービスを使用できますが、ゲストがアクセスできるのは、ホストが共有している特定のもののみです。 これには、コード、サーバーの実行、デバッグ セッション、ターミナルなどが含まれます。 現在、共有されるすべてのコンテンツはホストのマシン上に保持され、クラウドやゲストのマシンとは同期されません。これにより、"_簡単なアクセス_" と "_セキュリティの向上_" が実現されます。 その利点は、ゲストが参加した瞬間にソリューション全体が利用可能になること、またホストがコラボレーション セッションを終了した瞬間にコンテンツを利用できなくなることです。 さらに、ゲストのパフォーマンス向上のために IDE やエディターにより作成された一時ファイルは、セッション終了時に自動的にクリーンアップされます。

#### <a name="sharing"></a>共有

ホストとして "共有" する場合、プロジェクト、ソリューション、またはフォルダーの内容を共有するコラボレーション セッションを開始します。 ゲストは、ご自身が送信する招待リンクを使ってこのコンテンツへのアクセスを取得します。 "共有" は "プロジェクトを共有" の短縮形ですが、デバッグのような他の機能を共有するためにも使用されます。

**詳細情報:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-project) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-project)

#### <a name="joining"></a>結合

ホストから送信された招待リンクをクリックすると、ゲストとしてコラボレーション セッションに "参加" することができ、ホストが共有することを選択したすべてのコンテンツや機能にアクセスできます。 Web リンクにより、既に拡張機能をインストールしている場合はコラボレーション セッションを始めるための簡単な方法が、それ以外の場合は情報を設定するための簡単な方法が提供されます。

**詳細情報:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#join-a-collaboration-session) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#join-a-collaboration-session)

### <a name="features"></a>フィーチャー

#### <a name="co-editing"></a>共同編集

別のコラボレーターと同じファイルを開くと、すぐにそのファイルの内容を "共同編集" することができます。 各コラボレーターの編集内容や、各自のカーソルと選択などを確認できます。 さらに優れた点は、同じファイルの編集を常に強制されるわけではないため、自分の好きなように共同作業したり、単独で作業したりできるということです。

> [!NOTE]
> 共同編集にはいくつかの制限事項があります。 言語ごとの機能の状態については、[プラットフォームのサポート](../reference/platform-support.md)に関するページをご覧ください。

**詳細情報:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-editing) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-editing)

#### <a name="following-and-focusing"></a>フォローとフォーカス

複数のファイルやコード内の場所にまたがる問題や設計について説明する必要がある場合があります。 このような状況では、共同編集するときに、プロジェクト全体を移動する同僚を一時的にフォローすると便利な場合があります。 このため、ゲストは、コラボレーション セッションに参加するとホストの編集場所を自動的に "フォロー" します。 ホストとゲストは、簡単なマウス クリックでお互いのフォローを開始および終了できます。 さらに、すべての参加者に対して自分をフォローするよう求めたい場合があります。 Live Share では、フォローが返しやすくなる通知を使って、全員が自分に注意を "フォーカス" するよう要求することができます。

**詳細情報:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#following) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#following)

#### <a name="co-debugging"></a>共同デバッグ

厄介なコーディングの問題やバグをデバッグしているときに、それを見る人が増えると非常に役立ちます。 ホストである場合、Live Share により、すべてのゲストとデバッグ セッションを共有することで "共同デバッグ" が自動的に有効になります。 手順を実行しながら独自に調査する機能と共に、共同編集する機能がそれぞれに与えられます。

> [!NOTE]
> 言語またはプラットフォームごとのデバッグ機能の状態については、[プラットフォームのサポート](../reference/platform-support.md)に関するページをご覧ください。

**詳細情報:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-debugging) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-debugging)

#### <a name="share-server--share-port"></a>サーバーの共有 / ポートの共有

共同デバッグを行うとき、デバッグ セッション用にホストが提供するアプリケーションのさまざまな部分にアクセスできると非常に便利です。 ブラウザーでアプリにアクセスしたり、ローカル データベースにアクセスしたり、またはツールから REST エンドポイントを指定したりしたい場合があります。 Live Share では "サーバーを共有" することができます。これにより、ホストのマシン上のローカル ポートが、各ゲストのマシン上のまったく同じポートにマップされます。 次にゲストは、そのアプリケーションが自分のマシン上でローカルに実行されている場合とまったく同じように、それとやり取りすることができます (たとえば、ホストとゲストの両方が、次で実行される Web アプリにアクセスできます: http://localhost:3000) 。

**詳細情報:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-server) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-server)

#### <a name="share-terminals"></a>ターミナルの共有

最新の開発では、さまざまなコマンド ライン ツールを頻繁に使用します。 ありがたいことに、Live Share を使うとホストは必要に応じてゲストと "ターミナルを共有" することができます。 共有されたターミナルは、読み取り専用または完全な共同作業用にすることができます。このため、ホストとゲストの両方がコマンドの実行と結果の確認を行うことができます。 ホストは、他のコラボレーターが各自でコマンドを実行できるのか、またはただコマンドの出力を確認できるだけなのかどうかを、いつでも管理し、決定することができます。 実際、自分だけが確認したい操作は、すべて非共有のターミナルで実行できます。

**詳細情報:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-terminal) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-terminal)

#### <a name="access-controls"></a>アクセスの制御

Visual Studio Live Share では、共同作業のための優れた方法が参加者に多数提供されます。 しかし、ホストと対話するためにゲストに与えられるオプションの数や柔軟性を使って、参加するゲストを明示的に承認したり、特定のファイルやフォルダーへのアクセスをロックダウンしたりしたい場合があります。 Live Share には、読み取り専用やゲストの受け入れ要求など、役に立つさまざまな設定があります。

**詳細情報:** [![VS Code](../media/vscode-icon-15x15.png)](../reference/security.md) [![VS](../media/vs-icon-15x15.png)](../reference/security.md)

#### <a name="flexible-connection-modes"></a>柔軟な接続モード

最適なパフォーマンスを実現するために、Visual Studio Live Share では 2 つの主要な "接続モード": "直接" と "リレー" がサポートされています。 直接モードでは、ゲストは Web を経由せず直接ホストに接続します。 リレー モードを使うと、完全に別のネットワーク内にいるゲストが、インターネット リレーを経由してホストに接続できます。 すべての場合で、送受信される情報にコラボレーターのみがアクセスできるように、接続は SSH または SSL で暗号化されます。 既定では、Live Share は "自動" モードであり、最初に直接接続を試行してからリレーにフェールオーバーしますが、必要に応じて 1 つのモードにロックすることができます。

**詳細情報:** [![VS Code](../media/vscode-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode) [![VS](../media/vs-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode)
