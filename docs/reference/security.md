---
title: セキュリティ-Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live Share のセキュリティ機能について説明します。
ms.custom: ''
ms.date: 12/17/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 2f3a2adf0be13071f22a8ea7e33800af6f9099b5
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170105"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Live Share のセキュリティ機能

Visual Studio Live Share のコラボレーションセッションは、任意の数のユーザーがセッションに参加し、編集やデバッグなどを共同で行うことができるということで強力です。 ただし、このレベルのアクセス権を付与すると、Live Share 提供されているセキュリティ機能に関心があることは間違いありません。 この記事では、必要に応じて環境をセキュリティで保護するための推奨事項とオプションについて説明します。

**コラボレーションツールと同様に、コード、コンテンツ、およびアプリケーションは、信頼できるユーザーとのみ共有するようにしてください。**

## <a name="connectivity"></a>接続

Visual Studio Live Share のすべての接続は、SSH または SSL で暗号化され、中央サービスに対して認証され、コラボレーションセッション内のものだけがコンテンツにアクセスできるようにします。 既定では、Live Share は直接接続を試行し、ゲストとホスト間の接続が確立できない場合はクラウドリレーに戻ります。 Live Share の cloud relay では、トラフィックがどのようなトラフィックも保持されず、トラフィックを何らかの方法で "snoop" することはありません。 ただし、リレーを使用しない場合は、常に直接接続するように設定を変更できます。

これらの動作の変更と Live Share の接続要件の詳細については、「 **[Live Share の接続要件](connectivity.md)** 」を参照してください。

## <a name="invitations-and-join-access"></a>招待および参加へのアクセス

新しいコラボレーションセッションを開始するたびに、Live Share によって、招待リンクに配置される**新しい一意の識別子**が生成されます。 これらのリンクは、リンク内の識別子が "推測" ではなく、_単一のコラボレーションセッション中にのみ有効_であるため、信頼できる堅固なセキュリティで保護された基盤を提供します。

### <a name="removing-an-unexpected-guest"></a>予期しないゲストの削除

ホストとして、ゲストがコラボレーションセッションに参加するたびに自動的に通知されます。

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

さらに、通知を使用すると、何らかの理由で参加しているゲストを削除することができます。 (たとえば、会社全体のチャットシステムとランダムな従業員が参加している場合、誤ってリンクを投稿した場合など)。表示される通知の [削除] ボタンをクリックするだけで、コラボレーションセッションから取り出すことができます。

**VS Code**では、参加通知を破棄した場合でも、その後の参加者を削除することもできます。 エクスプローラーまたは VS Code アクティビティバーの [カスタム] タブで Live Share ビューを開くと、参加者の名前をポイントするか右クリックして、[参加者の削除] アイコンまたはオプションを選択できます。

![VS Code の参加者の削除](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>ゲストの承認が必要

通常、コラボレーションセッションに参加する参加者は、Microsoft の職場または学校のアカウント (AAD)、個人用 Microsoft アカウント、または GitHub アカウントを使用して**Live Share にサインイン**します。 サインインしているユーザーに対する "通知 + 削除" の既定値を使用すると、これらのゲストに対して速度と制御が優れていますが、重要な操作を行っている場合は、少しだけ**ロック**を解除することができます。

また、特定の状況では、すべてのゲストがコラボレーションセッションに参加するために強制的にサインインすることが問題になる場合があります。 例として、ゲスト、教室/学習シナリオ、またはサポートされているアカウントの種類のいずれかを持たないユーザーと共同で参加するために、Live Share の新しいユーザーに依頼することがあります。 これらの理由により、Live Share は、サインインして**いない**ユーザーがコラボレーションセッションに**読み取り**専用のゲストとして参加できるようにすることができます。 ホストは、これらのゲストが既定で参加できるようになる前に、これらのゲストを**承認**する必要がありますが、これらの "匿名" ゲストを許可しないか、常に承認することをお勧めします。

#### <a name="requiring-guest-approval-for-signed-in-users"></a>サインインしているユーザーに対してゲスト承認を要求する

サインインしているゲストが "承認済み" になるまでコラボレーションセッションに参加できないようにするには、次の設定を変更します。

* **VS Code**で、次のように設定します。 Json (ファイル > 設定 > 設定) に追加します。

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* **Visual Studio**で [ツール] > [オプション] > 設定し Live Share > "ゲスト承認が必要" になります。

    ![ゲスト承認設定が強調表示されている Visual Studio の設定ウィンドウ](../media/vs-setting-guestapproval.png)

この時点以降、参加している各ゲストを承認するように求められます。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-approval.png" width="100%" alt="Visual Studio Code join approval request" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-approval.png" width="100%" alt="Visual Studio join approval request"/>
    </td>
</tr>
</table>

ゲストとして、ホストでこの設定が有効になっているセッションに参加すると、ステータスバーまたは参加ダイアログが表示され、Live Share がホストの承認を待機していることが通知されます。

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>サインインしていないユーザーを自動的に拒否または受け入れる (匿名)

前述のように、Live Share は、サインインして**いないユーザー**がコラボレーションセッションに**読み取り**専用のゲストとして参加することを許可するように構成できます。  これらの **"匿名" ゲストは参加時に名前を入力する必要があり**ますが、単純な名前では実際のサインインと同じレベルの保証は提供されません。 したがって、既定では、ホストは、前述の "ゲスト承認が必要" 設定に関係なく、匿名ゲスト**を承認するように求められ**ます。

次のようにして、**常に拒否**する (匿名ゲストを無効にする) か、匿名ユーザーを**受け入れる**ことができます。

* **VS Code**で、必要に応じて `accept`、`reject`、または `prompt` (既定値) に `liveshare.anonymousGuestApproval` を設定 > > します。

* **Visual Studio**で、[ツール] > [オプション] > Live Share > "Anonymous guest approval" を設定して、必要に応じて同意、拒否、またはプロンプト (既定) に設定します。

 **ただし、信頼できる相手には Live Share 招待のリンクのみを送信する必要があることに注意してください。**

## <a name="controlling-file-access-and-visibility"></a>ファイルアクセスと可視性の制御

ゲストとして Live Share のリモートモデルを使用すると、プロジェクトの内容全体を同期することなく、ホストが共有しているファイルやフォルダーに対する読み取り/書き込みアクセスをすばやく行うことができます。 そのため、共有ファイルツリー全体のファイルを個別に移動して編集できます。 **ただし、この自由度によってホストに何らかのリスクが生じます。** 概念としては、開発者は知識を必要とせずにソースコードを変更したり、共有ファイルツリーのどこかにある機密ソースコードや "シークレット" を参照したりすることもできます。 そのため、ホストとして、共有するプロジェクト全体にゲストがアクセスできるようにする必要はない場合があります。 さいわいにも、このリモートモデルの利点は、機能を犠牲にせずに、共有したくないファイルを "除外する" ことを選択できることです。 ゲストは、通常、これらのファイルへのアクセスを必要とするデバッグセッションなどに参加できます。

これを行うには、共有するフォルダーまたはプロジェクトに**vsls. json**ファイルを追加します。 この json 形式のファイルに追加した設定によって、Live Share がファイルを処理する方法が変わります。 直接制御を提供するだけでなく、これらのファイルをソース管理にコミットすることもできます。これにより、プロジェクトの複製を行うユーザーは、追加の作業を行わずにこれらの規則を利用できるようになります。

次に例を示します。 vsls. json ファイル:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"none",
    "excludeFiles":[
        "*.p12",
        "*.cer",
        "token",
        ".gitignore"
    ],
    "hideFiles": [
        "bin",
        "obj"
    ]
}
```

> [!NOTE]
> また、コラボレーションセッションを開始するときに、すべてのファイル/フォルダーを**読み取り**専用として設定することもできます。 詳細については、[以下](#read-only-mode)を参照してください。

これらのプロパティがどのように変更されるかについて説明します。

### <a name="properties"></a>プロパティ

**Excludefiles**プロパティを使用すると、特定のファイルやフォルダーがゲストに対して開かれるのを Live Share 防ぐために、glob ファイルパターンのリスト (ファイルが見つかった場合とよく似たもの) を指定できます。 これには、ゲストの_フォローや編集場所へのジャンプ、共同デバッグ中のファイルのステップ実行、定義へ移動などのコードナビゲーション機能_などのシナリオが含まれていることに注意してください。 シークレット、証明書、またはパスワードが含まれている場合など、どのような状況でも共有したくないファイルを対象としています。 たとえば、はセキュリティを制御するため、vsls ファイルは常に除外されます。

**Hidefiles**プロパティは類似していますが、厳密ではありません。 これらのファイルは、単純にファイルツリーから非表示になります。 たとえば、デバッグ中にこれらのファイルのいずれかにステップインすると、エディターで開いたままになります。 このプロパティは、(別のソース管理システムを使用している場合のように) ファイルの設定がない場合、または複雑で混乱を避けるために、既に存在しているものを単に拡張したい場合に、主に役立ちます。

**.Gitignore**は、共有フォルダー内のファイルの内容を Live Share がどのように処理するかを設定します。 既定では、glob ファイルで見つかったすべてのファイルは、"hideFiles" プロパティで指定されているかのように扱われます。 ただし、次のいずれかの値を使用して別の動作を選択することもできます。

| オプション    | 結果                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | ファイルツリー内のゲストは、内容を表示できます (ゲストエディターの設定によってフィルター処理されていないことを前提としています)。 |
| `hide`    | **既定値。** Glob の内部では、"hideFiles" プロパティにあるかのように処理されます。                   |
| `exclude` | Glob の内部では、"excludeFiles" プロパティに含まれているかのように処理されます。                                 |

`exclude` 設定の欠点は、node_modules のようなフォルダーの内容が頻繁に使用されることですが、デバッグ中にステップインすると便利です。 そのため、Live Share は、excludeFiles プロパティで "!" を使用してルールを反転する機能をサポートしています。 たとえば、次の例では、node_modules を除き、"gitignore に含まれるすべてのものが除外されます。

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

Hide および exclude の各ルールは個別に処理されるので、実際に除外しないで node_modules を非表示にしたい場合は、次のようにファイルを編集するだけで済みます。

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ],
    "hideFiles":[
        "node_modules"
    ]
}
```

### <a name="vslsjson-files-in-sub-folders"></a>サブフォルダー内の vsls json ファイル

最後に、のように、ファイルをサブフォルダーに配置することもできます。 Hide/exclude 規則は、共有しているルートフォルダー (存在する場合) にある vsls. json ファイルから開始し、各サブフォルダーで、処理する vsls ファイルを検索するために指定されたファイルの先頭に移動することによって決定されます。 ファイルツリーの下位にあるフォルダー内の vsls の json ファイルの内容は、上位レベルで設定された規則を補完 (またはオーバーライド) します。

### <a name="disabling-external-file-sharing"></a>外部ファイル共有の無効化

既定では、共有フォルダー/ソリューションの外部にあるホストが開くすべてのファイルも、Live Share によって共有されます。 これにより、再度共有しなくても、他の関連ファイルを簡単に開くことができます。

この機能を無効にする場合は、次のようにします。

* **VS Code**で、次の値を設定. json に追加します。

    ```json
    "liveshare.shareExternalFiles": false
    ```

* **Visual Studio**では、[ツール] &gt; オプション &gt; Live Share &gt; "外部ファイルの共有" を False に設定します。

## <a name="read-only-mode"></a>読み取り専用モード

場合によっては、コードをホストとして共有するときに、ゲストが編集を行わないようにする必要があります。 一部のコードを確認するためにゲストが必要になる場合や、プロジェクトが多数のゲストに表示されていて、不要または偶発的な編集が行われないようにしたい場合があります。 Live Share には、読み取り専用モードでプロジェクトを共有する機能が用意されています。

ホストとして共有する場合、コラボレーションセッションで読み取り専用モードを有効にするオプションがあります。 ゲストが参加している場合、コードを編集することはできませんが、他のユーザーのカーソルと強調表示を確認しながら、プロジェクト内を移動することはできます。

読み取り専用モードの場合でも、ゲストとの共同デバッグを行うことができます。 ゲストはデバッグプロセスをステップ実行することはできませんが、ブレークポイントを追加または削除したり、変数を検査したりすることはできます。 また、サーバーと端末 (読み取り専用) をゲストと共有することもできます。

読み取り専用コラボレーションセッションを開始する方法の詳細については、 [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-project) [![](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-project)を参照してください。

## <a name="co-debugging"></a>共同デバッグ

コーディングに関する問題やバグを克服する際には、デバッグ時に目のペアが非常に役に立つことがあります。 Visual Studio Live Share では、ホストがデバッグを開始するたびに、すべてのゲストとのデバッグセッションを共有することによって、"コラボレーションデバッグ" または "共同デバッグ" を有効にします。

ホストとしては、デバッグセッションの開始時または停止時に完全に制御できますが、信頼されていないユーザーと共有している場合は、共同デバッグによって何らかのリスクが生じます。 Live Share を使用すると、ゲストがコンソール/REPL コマンドを実行できるようになり、悪意のある**アクターが実行する必要のないコマンドを実行する危険性**があります。

そのため、**信頼できるものとのみ、デバッグ**する必要があります。

詳細情報: [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-debugging) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>ローカルサーバーの共有

共同デバッグを行うとき、デバッグ セッション用にホストが提供するアプリケーションのさまざまな部分にアクセスできると非常に便利です。 ブラウザーでアプリにアクセスしたり、ローカルデータベースにアクセスしたり、ツールから REST エンドポイントをヒットしたりすることができます。 Live Share を使用すると、ホストのマシン上のローカルポートをゲストのコンピューター上のまったく同じポートにマップする "サーバーを共有" できます。 ゲストとして、コンピューター上でローカルに実行されているかのようにアプリケーションと完全に対話できます (たとえば、ホストとゲストは http://localhost:3000) で実行されている web アプリにアクセスできます)。

ただし、ホストとしては、ゲストと**共有するポートを選択**し、システムポートではなくアプリケーションポートのみを共有することをお勧めします。 ゲストから見ると、共有ポートは、サーバー/サービスが自分のコンピューターで実行している場合とまったく同じように動作します。 これは非常に便利ですが、共有するポートを間違えると危険な場合もあります。 このため、Live Share は、構成設定およびホストがアクションを実行することなく、共有する必要があるかどうかを想定しているわけではありません。

Visual Studio では、ASP.NET プロジェクトで指定された**web アプリケーションポート**は、の実行時に web アプリへのゲストアクセスを容易にするために、**デバッグ中にのみ自動的に共有**されます。 ただし、必要に応じて、[ツール] > [オプション] > Live Share > [デバッグ時に web アプリを共有] を [False] に設定すると、この自動化を無効にすることができます。

Visual Studio Code では、Live Share**適切なアプリケーションポートの検出**と共有を試行します。 ただし、次のものを設定に追加することで無効にできます。

        liveshare.autoShareServers: false

どちらの場合も、追加のポートを共有するときは注意が必要です。

機能の構成の詳細については、「 [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-server) 」 [![](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-server) 「」を参照してください。

## <a name="sharing-a-terminal"></a>ターミナルを共有する

最新の開発では、さまざまなコマンド ライン ツールを頻繁に使用します。 ありがたいことに、Live Share を使うとホストは必要に応じてゲストと "ターミナルを共有" することができます。 共有されたターミナルは、読み取り専用または完全な共同作業用にすることができます。このため、ホストとゲストの両方がコマンドの実行と結果の確認を行うことができます。 ホストとして、他のコラボレーターが出力を表示するか、任意の数のコマンドラインツールを使用して、テストの実行、ビルド、または環境固有の問題のトリアージを行うことができます。

ゲストが起動しないようにするために、共有ターミナルを開始できるのはホストだけです。 共有ターミナルをホストとして起動するときに、読み取り専用または読み取り/書き込みのどちらであるかを指定できます。 ターミナルが読み取り/書き込みのときは、ホストを含むすべてのユーザーがターミナルに入力でき、ゲストが好ましくないことを行っている場合は簡単に介入できます。 ただし、安全のため、ホストは、**読み取り/書き込みアクセスはゲストが実際にそれを必要としていることがわかっている場合にのみ許可**し、自分が実行するコマンドの出力をゲストに見せたいだけの場合は読み取り専用ターミナルを使用する必要があります。

Visual Studio では、既定では、ターミナルは共有されません。 VS Code では、ターミナルは既定で**読み取り**専用として自動的に共有されます。 ただし、次のものを設定に追加することで無効にできます。

```json
"liveshare.autoShareTerminals": false
```

詳細情報: [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-terminal) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>AAD 管理者の同意

Microsoft の**勤務先または学校の電子メールアドレス**を使用してサインインすると、サインイン時に **"管理者の承認が必要です"** というメッセージが表示される場合があります。 これは、Live Share がセキュリティ機能のためにユーザー情報への読み取りアクセスを必要とし、Azure AD テナントがディレクトリのコンテンツにアクセスする新しいアプリケーションに "管理者の同意" を要求するように設定されているためです。

AD 管理者は、次の情報を使用して、このことを解決する必要があります。

* **アプリケーション名**: Visual Studio Live Share (insider)
* **アプリケーションの種類**: Web アプリ
* **アプリケーションの状態**: 運用
* 委任された**アクセス許可**: ユーザー。読み取り
* **アプリケーション URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **応答 URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

これは、Live Share を使用するすべてのユーザーに対して1回だけ行う必要があります。 詳細については、こちらと[こちら](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal)を[参照して](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes)ください。

## <a name="see-also"></a>関連項目

* [方法: Visual Studio Code を使用したコラボレーション](../how-to-guides/vscode.md)
* [方法: Visual Studio を使用して共同作業する](../how-to-guides/vs.md)
* [Live Share の接続要件](connectivity.md)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
