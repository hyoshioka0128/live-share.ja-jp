---
title: セキュリティ - Visual Studio の Live Share |Microsoft Docs
description: Visual Studio Live Share のセキュリティ機能に関する情報です。
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
ms.openlocfilehash: 754a740118ef9e6de2463fb3bb0537af350409aa
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640199"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Live Share のセキュリティ機能

Visual Studio Live Share で共同作業セッションは、ユーザー セッションに参加し、共同編集、デバッグなどの任意の数を許可するという点で強力です。 ただし、このレベルのアクセスを付与するには、間違いなく対象となる Live Share を提供するセキュリティ機能。 この記事で推奨事項と、必要に応じて、環境をセキュリティで保護するためのオプションを提供いたします。

**任意のコラボレーション ツールと同様、コード、コンテンツ、およびアプリケーションを信頼できる人とを共有する必要がありますのみことに注意してください。**

## <a name="connectivity"></a>接続

Visual Studio Live Share のすべての接続は、ことコラボレーション セッションでのみ、そのコンテンツへのアクセスができることを確認するには、SSH または SSL 暗号化され、中央のサービスに対して認証されます。 既定では、Live Share は直接接続を試行し、ゲストとホスト間の接続を確立できない場合に、クラウドのリレーに頼る。 Live Share のクラウド リレーを経由してルーティングの任意のトラフィックは保持されませんはない「覗き見」任意の方法でトラフィックに注意してください。 ただし、リレーを使用しないようにする場合は、常に直接接続する設定を変更できます。

これらの動作と Live Share の接続要件の変更の詳細については、次を参照してください。  **[Live Share の接続要件](connectivity.md)** します。

## <a name="invitations-and-join-access"></a>招待および参加アクセス

新しいコラボレーション セッションを開始するたびに、Live Share を生成、**新しい一意の識別子**は、この招待リンクに配置されます。 これらのリンクがリンク内の識別子が「非推測」し、信頼できるユーザーを招待する強固で安全な基盤を提供_単一コラボレーション セッションの期間に対してのみ有効です_します。

### <a name="removing-an-unexpected-guest"></a>予期しないゲストを削除します。

ホストとして、ゲストが共同作業セッションに参加するたびに自動的に通知されます。

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

さらに良いことを通知できるようにする何らかの理由がわからない場合に参加してゲストを削除します。 (たとえば、会社全体のチャット システムに誤って、リンクを投稿した、ランダムな従業員が参加している場合。)単に表示される通知の「削除」ボタンをクリックし、共同作業セッションから排出されます。

**VS Code**、その後、参加要素を削除する機能もがある場合でも、結合通知を閉じます。 Live Share ビューを開き、エクスプ ローラーまたは VS Code アクティビティ バーでユーザー設定 タブで、ポインターを合わせるまたは参加要素の名前を右クリックし、「参加要素の削除」アイコンまたはオプションを選択することができます。

![VS Code で参加者を削除します。](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>ゲストの承認を必要とします。

通常、コラボレーション セッションに参加する参加要素に**Live Share にサインイン**Microsoft の職場または学校アカウント (AAD)、個人の Microsoft アカウントまたは GitHub アカウントを使用します。 「通知 + 削除」の中に既定のユーザーのサインインは適切な組み合わせを提供しますの速度とこれらのゲストを制御することも**ものをロック ダウン**機密性の高いものを実行している場合は、少し詳細。

さらに、コラボレーションの参加にサインインするすべてのゲストを強制する特定の状況でセッションを問題となることができます。 例としては、guest、教室/学習のシナリオとして結合する Live Share を新しいユーザーを確認するか、サポートされている勘定科目の種類のいずれかを持っていないユーザーのユーザーと共同作業を行うときにします。 これらの理由から、Live Share があるユーザーを許可できます**サインインしていない**として共同作業セッションに参加する**読み取り専用**ゲストです。 ホストをする必要があります**承認**既定でに参加させる前にこれらのゲスト「匿名」これらのゲストを許可しないか、代わりに常に承認する可能性があります。

#### <a name="requiring-guest-approval-for-signed-in-users"></a>ユーザーをサインインのゲストの承認を必要とします。

防ぐためにサインインして、コラボレーションまで、「承認された」には、セッションに参加したり、ゲストをたい場合は、次の設定を変更します。

* **VS Code**settings.json に次の追加 (ファイル > 設定 > 設定)。

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* **Visual Studio**ツールの設定 > オプション > Live Share >「を True にゲストの承認が必要」です。

    ![ゲストの承認の設定が強調表示されているで、visual Studio の設定ウィンドウ](../media/vs-setting-guestapproval.png)

この時点以降は、承認を結合する各ゲストに求め。

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

ゲストとしてホストが有効にすると、この設定には、セッションに参加する場合、ステータス バーに通知されますか参加を承認するホストを待機している Live Share ダイアログ。

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>サインインしていない (匿名) 自動拒否または受け入れ側のユーザー

許可する Live Share を構成することが前述のよう**で署名されていないユーザー**として共同作業セッションに参加する**読み取り専用**ゲストです。  これらを while **「匿名」ゲストは、名前を入力する必要があります**簡易名が同じレベルの実際のサインインと保証を行いませんを結合するとき。 そのため、**既定では、ホストが承認するように求め**「ゲストの承認を要求する」に関係なく、匿名のゲスト上の説明を設定します。

できます**常に拒否**(匿名のゲストを無効にする) または**常にそのまま使用**匿名ユーザーとして次のとおりです。

* **VS Code**設定`liveshare.anonymousGuestApproval`settings.json で (ファイル > の基本設定 > 設定) に`accept`、 `reject`、または`prompt`(既定) に応じて。

* **Visual Studio**ツールの設定 > オプション > Live Share >"許可を匿名のゲスト approval"、拒否、またはプロンプト (既定値) として適切な。

 **Live Share を送信する必要がありますのみに関係なく、記憶する人を招待へのリンクを信頼します。**

## <a name="controlling-file-access-and-visibility"></a>ファイルへのアクセスと可視性を制御します。

ゲストとして Live Share のリモートのモデルにアクセスできますクイック読み取り/書き込みファイルとフォルダー、プロジェクトの内容全体を同期することがなく、ホストを共有しました。 したがって個別に移動でき、全体の共有ファイル ツリー内のファイルを編集できます。 **ただし、この自由度は、ホストにいくつかリスクを伴います。** 概念、開発者移動し、知らない間にソース コードを変更または機密性の高いソース コードまたは共有のファイル ツリー内のどこかにある「シークレット」を参照してくださいすることでした。 その結果、ホストが、常にしない場合、ゲストが共有しているプロジェクトの全体にアクセスします。 さいわいにも、このリモート モデルの利点は、機能を損なうことがなく、誰と共有したくないファイルを"exclude"することを選択できます。 ゲストは、セッションは通常必要とするこれらのファイルへのアクセスする必要がある場合を行うには、独自のデバッグなどの項目に参加できます。

これを実現するには追加することを **. vsls.json**フォルダーまたは共有しているプロジェクト ファイル。 この json 形式のファイルに追加するすべての設定は、Live Share がファイルを処理する方法を変更します。 直接制御を提供し、これらのファイルもコミットできますをソース管理に活用するために何も追加の作業でこれらのルールでは、プロジェクトを複製するすべてのユーザーができるようにします。

例を次に示します。 vsls.json ファイル。

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
> 共有するすべてのファイル/フォルダーを作成することも**読み取り専用**コラボレーション セッションを開始するときにします。 参照してください[下](#read-only-mode)詳細についてはします。

これらのプロパティがゲストで実行できる内容を変更する方法を見てみましょう。

### <a name="properties"></a>プロパティ

**ExcludeFiles**プロパティでは、(非常に .gitignore ファイルが検出されたものと同様) glob のファイル パターンの一覧を指定できます。 Live Share をゲストの特定のファイルまたはフォルダーを開くようにします。 ゲストのようなシナリオを含むはこのことに注意して_任意のコード ナビゲーション機能などの定義、および詳細に移動後またはファイルへの共同作業のデバッグ中にステップ イン、編集場所にジャンプします。_ 共有シークレット、証明書、またはパスワードを格納しているような状況にかかわらずしないファイルに適しています。 セキュリティを制御するためなどです。 vsls.json ファイルは常に除外します。

**HideFiles**プロパティと同様がないほど厳格です。 これらのファイルは、ファイル ツリーからは見えませんだけです。 発生する場合など、デバッグ中に、これらのファイルのいずれかにステップ インにはまだエディターで開きます。 など、さまざまなソース管理システムを使用している場合場合のもの) は、.gitignore ファイルのセットアップを持たない場合、または単に何が既にある混乱を回避するために拡張する場合、このプロパティは主に役立ちます。

**Gitignore**設定は、Live Share が共有フォルダーの .gitignore ファイルの内容を処理する方法を確立します。 既定では、.gitignore ファイルで見つかった任意の glob は"hideFiles"プロパティで指定された場合と同様に扱われます。 ただし、値は次のいずれかを使用してさまざまな動作を選択できます。

| オプション    | 結果                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | .gitignore の内容は、ゲスト (ゲスト エディターの設定によってフィルター処理されないと仮定) のファイル ツリー内に表示されます。 |
| `hide`    | **既定値です。** Glob .gitignore 内では、"hideFiles"プロパティであったかのように処理されます。                   |
| `exclude` | Glob .gitignore 内では、"excludeFiles"プロパティであったかのように処理されます。                                 |

欠点、`exclude`設定は node_modules などのフォルダーの内容が .gitignore が頻繁には、デバッグ中にステップ インに役に立ちます。 Live Share がルールを使用して、反転する機能をサポートするそのため、"!"excludeFiles プロパティ。 たとえば、この。 node_modules を除き".gitignore"内のすべて vsls.json ファイルは除外します。

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

見やすくするために実際に除外せず node_modules を非表示にする場合は、編集できるように単にファイルとしては、次のように、非表示にして、除外するルールが個別に処理されます。

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

### <a name="vslsjson-files-in-sub-folders"></a>。 サブフォルダーに vsls.json ファイル

最後に、.gitignore と同様します。 vsls.json ファイルをサブフォルダーに配置することができます。 非表示にする/除外する規則以降によって決定されます、。 vsls.json ファイル (ある場合) を共有したルート フォルダーおよびしを示しながら各サブ フォルダーにある先頭から検索する特定のファイルにします。 vsls.json ファイルを処理します。 内容。 vsls.json ファイル、ファイル ツリーの下位のフォルダーでし補完 (またはオーバーライド) より高いレベルで設定された規則。

### <a name="disabling-external-file-sharing"></a>外部ファイル共有を無効にします。

既定では、も、Live Share と外部共有のフォルダーにあるホストを開きますファイルを共有は/ソリューション。 これにより、簡単にすばやく再共有することがなく他の関連ファイルを開きます。

この機能を無効にする場合は。

* **VS Code**settings.json に以下を追加します。

    ```json
    "liveshare.shareExternalFiles": false
    ```

* **Visual Studio**、ツール設定&gt;オプション&gt;Live Share &gt; 「外部ファイルを共有」を False に

## <a name="read-only-mode"></a>読み取り専用モード

ホストとして、コードを共有する場合、ゲスト編集を行うには必要ありません。 ゲスト、コードのいくつかを確認する必要があります。 または多数のゲストをプロジェクトを表示し、不要なや偶発的な編集をしたくないです。 ライブの共有は、読み取り専用モードでプロジェクトを共有する機能を提供します。

ホスト、共有する場合は、としては、コラボレーション セッションを読み取り専用モードを有効にするオプションがあります。 ゲストに参加する場合では、する他のカーソルを引き続き参照できますと強調表示だけでなく、プロジェクト内を移動する場合に、コードに変更を加えることはできません。

読み取り専用モードでのゲストと併置デバッグできますも。 ゲストには、デバッグのプロセスの手順がまだを追加または、ブレークポイントを削除したり変数を検査する機能はありません。 さらに、ゲストでまだサーバーとターミナル (読み取り専用) を共有することができます。

読み取り専用のコラボレーション セッションを開始する方法の詳細を確認できます。[![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-project) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-project)

## <a name="co-debugging"></a>共同デバッグ

大変なコーディングの問題やバグをどう取り組んでいるときにデバッグするときに、目の追加のペアを持つは本当に役に立ちます。 Visual Studio Live Share は、"共同デバッグ機能"またはホストでのデバッグを開始するたびに、すべてのゲストで、デバッグ セッションを共有することで「デバッグ併置」を使用できます。

ホストが完全に制御経由でデバッグ セッションを開始または停止されますが、併置デバッグ発生することは危険性を信頼していない人と共有している場合。 ライブ共有により、ゲスト コンソール/REPL コマンドを実行するように招待して、したがってが**しない実行するようにコマンドを実行して、悪意のあるアクターのリスク**します。

その結果、**のみを信頼するとデバッグ併置します。**

詳細情報：[![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-debugging) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>ローカル サーバーの共有

共同デバッグを行うとき、デバッグ セッション用にホストが提供するアプリケーションのさまざまな部分にアクセスできると非常に便利です。 ブラウザーでアプリへのアクセス、ローカルのデータベースへのアクセスや、ツールからの REST エンドポイントをヒットする可能性があります。 ライブの共有を使用して、"share、サーバー"のゲスト マシン上の正確な同じポートをホストのマシンのローカル ポートにマップすることができます。 ゲストとしてすることができますと対話し、アプリケーション コンピューターにローカルで実行されていた場合とまったく同様 (例: ホストとゲスト両方アプリにアクセスできる、web で実行されている http://localhost:3000)します。

ただし、ホストにする必要があります**するポートを共有すると非常に高い**アプリケーション ポートではなくシステムのポートをゲストとのみ共有します。 ゲストから見ると、共有ポートは、サーバー/サービスが自分のコンピューターで実行している場合とまったく同じように動作します。 これは非常に便利ですが、共有するポートを間違えると危険な場合もあります。 このため、Live Share を何かなしの構成設定とアクションを実行するホストは共有できませんを想定することはありません。

Visual Studio で、 **web アプリケーション ポート**ASP.NET プロジェクトで指定された、**のみのデバッグ時に自動的に共有**を実行するときに、web アプリへのゲスト アクセスを容易にします。 ただし、ツールを設定してこの自動化オフにできます > オプション > Live Share >「共有 web アプリのデバッグ」したい場合は"False"にします。

Visual Studio Code での Live Share を試みます**適切なアプリケーションのポートを検出**と共有できます。 ただし、これを settings.json に以下を追加して無効できます。

        liveshare.autoShareServers: false

どちらの場合に、追加のポートを共有する場合、注意を実行します。

ここで、機能の構成に関する詳細を確認できます。[![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-server) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>共有ターミナル

最新の開発では、さまざまなコマンド ライン ツールを頻繁に使用します。 ありがたいことに、Live Share を使うとホストは必要に応じてゲストと "ターミナルを共有" することができます。 共有されたターミナルは、読み取り専用または完全な共同作業用にすることができます。このため、ホストとゲストの両方がコマンドの実行と結果の確認を行うことができます。 ホストとするか、その他の共同作業者は、出力だけ参照してください。 または、コマンドラインの任意の数を使用するか、ビルド、テストを実行するためのツールが環境に固有の問題をトリアージを許可することができました。

ホストだけでは、1 つの起動となくを指定してください、監視を行ってからゲストを防ぐために共有端末を開始できます。 共有ターミナルとしてホストを開始するかどうかにする読み取り専用か読み取り/書き込みを指定できます。 ターミナルが読み取り/書き込みのときは、ホストを含むすべてのユーザーがターミナルに入力でき、ゲストが好ましくないことを行っている場合は簡単に介入できます。 ただし、安全のため、ホストは、**読み取り/書き込みアクセスはゲストが実際にそれを必要としていることがわかっている場合にのみ許可**し、自分が実行するコマンドの出力をゲストに見せたいだけの場合は読み取り専用ターミナルを使用する必要があります。

Visual Studio で終端要素は、既定では共有されません。 VS Code で、端末が自動的に共有**読み取り専用**既定。 ただし、これを settings.json に以下を追加して無効できます。

```json
"liveshare.autoShareTerminals": false
```

詳細情報：[![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-terminal) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>AAD 管理者の同意

バックアップ、Microsoft を使ってサインインするときに**職場または学校の電子メール アドレス**メッセージが表示される **「管理者の承認が必要」** サインインするときにします。 Live Share のセキュリティ機能のユーザー情報への読み取りアクセスを必要として、ディレクトリの内容にアクセスする新しいアプリケーションの「管理者の同意」を必要とする Azure AD テナントをよう設定されているためにです。

AD の管理者を次の情報を使用してこれを解決する必要があります。

* **アプリケーション名**:Visual Studio Live Share (Insider)
* **アプリケーションの種類**:Web アプリ
* **アプリケーションの状態**:実稼働
* **委任されたアクセス許可**:User.Read
* **アプリケーションの URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **応答 URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

Live Share を使用しているユーザーの 1 回実行するこのはだけです。 参照してください[ここ](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes)と[ここ](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal)詳細についてはします。

## <a name="see-also"></a>関連項目

* [方法:Visual Studio Code を使用して共同作業する](../use/vscode.md)
* [方法:Visual Studio を使用して共同作業する](../use/vs.md)
* [Live Share の接続要件](connectivity.md)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
