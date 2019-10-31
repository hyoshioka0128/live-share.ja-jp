---
title: 接続-Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live Share の接続モードと接続モードについて説明します。
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: c1d537ac80daddcf83d18942c8d837f3c0ce370b
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73169990"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Live Share の接続性要件

この記事では、Visual Studio Live Share の接続要件、使用可能な接続オプション、および該当する場合の既知の回避策について説明します。

## <a name="sign-in"></a>サインイン

Live Share にサインインするには、 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory)バックアップされた職場または学校アカウント、 [Microsoft アカウント](https://account.microsoft.com/account)、または[GitHub プロファイル](https://github.com/)を使用します。 通常、このような場合のサインイン Url は、それらを使用する公開製品の数によって、ほとんどの組織で開かれていますが、そうでない場合は、ネットワーク管理者に連絡して、[以下](#requirements-for-connection-modes)のドメインに加えて `login.microsoftonline.com` や `github.com` を開くことを依頼してください。

> [!NOTE]
> オンプレミス AD (ADFS) アカウントとオンプレミスの GitHub エンタープライズアカウントは、現在サポートされていません[(アップ投票 👍)](https://github.com/MicrosoftDocs/live-share/issues/341)。

## <a name="connection-modes"></a>接続モード

最適なパフォーマンスを得るために、既定では Visual Studio Live Share は、コラボレーションセッションホストコンピューターとゲストコンピューターがネットワーク経由で直接通信できるかどうかを自動的に検出し、それらの間にルートがない場合はクラウド経由でのみリレーします。 このように混合された "自動" モードは柔軟であり、一部のゲストはクラウド経由でリレーでき、他のゲストは同じセッションに直接接続できます。

直接接続は、セキュリティを確保するためにクラウドベースのメカニズムを使用して認証されますが、接続を有効にするために5990と5999の間にポートを開く必要があります。 このため、最初にデスクトップファイアウォールでポートを開くように求めるメッセージが表示されたときに共有すると、 この指定は省略できます。これを無視すると、auto モードのときに Live Share が常にリレーを使用するようになります。

Visual Studio Live Share のすべての接続は、SSH または SSL で暗号化され、中央サービスに対して認証され、コラボレーションセッション内のものだけがコンテンツにアクセスできるようにします。 さらに、Live Share のクラウドリレーでは、トラフィックがルーティングされることはなく、トラフィックをどのような方法でも "snoop" することはありません。

## <a name="changing-the-connection-mode"></a>接続モードの変更

直接接続またはリレー接続を無効にしたい場合や、接続の問題のトラブルシューティングを行う場合は、他の接続モードを強制することができます。

| モード | ホストの動作 | ゲストの動作 |
|------|----------------|----------------------|
| 自動 | ホストのコラボレーションセッションは、セキュリティで保護された、認証された直接接続またはクラウドリレー接続を受け入れます。 | は、直接接続を使用しようとし、失敗した場合には、クラウドのリレーにフォールバックします。 |
| 直接 | ホストのコラボレーションセッションでは、認証された安全な直接接続のみが受け入れられます。 | 直接接続の使用を試み、接続できない場合は停止します。 |
| Relay | ホストのコラボレーションセッションでは、直接接続は許可されていません。 ホストのコンピューターでポートが開かれていません。 | 常にクラウド経由で接続します。 |

モードを変更するには:

**VS>**

1. ツール > オプション > Live Share にアクセスします。
2. [接続モード] ドロップダウンからモードを選択します。
3. VS を再起動します。

**VS Code：**

1. [設定の編集] (ファイル > 基本設定 > 設定) を編集します。
2. 設定に応じて、`"liveshare.connectionMode"` を `"auto"`、`"direct"`、または `"relay"` に設定します。
3. VS Code を再起動します。

## <a name="requirements-for-connection-modes"></a>接続モードの要件

使用する接続モードによって、Live Share が機能するために使用する必要がある特定のポートと Url が決まります。

| モード | クライアントアクセス要件 | トラブルシューティング |
|------|--------------|-----------------|
| どれでも可 | `*.liveshare.vsengsaas.visualstudio.com:443` への発信アクセス | 企業または個人のネットワークファイアウォールで、このドメインに接続できることを確認します。 ブラウザーで https://insiders.liveshare.vsengsaas.visualstudio.com を入力し、Visual Studio Live Share のホームページに移動していることを確認します。 また、解決する必要がある[プロキシの問題](#proxies)が発生している可能性があります。|
| 任意 (VS Code) | `download.microsoft.com:443` への発信アクセス | 企業または個人のネットワークファイアウォールで、このドメインに接続できることを確認します。 また、解決する必要がある[プロキシの問題](#proxies)が発生している可能性があります。 |
| 自動 | 自動スイッチ。 「直接モードとリレーモード」を参照してください。 | 直接モードまたはリレーモードに切り替えて、トラブルシューティングを行います。 |
| 直接 | ホスト: 受信ローカルネットワーク接続を受け入れるには、5990 ~ 5999 の範囲のポートを開く必要があります。<br /><br />ゲスト: この同じポートでのホストへのネットワークルートと発信アクセス。 | このポート範囲のデスクトップファイアウォールソフトウェアによって "vsls-agent" がブロックされていないこと、および ping を実行できることを確認してください。 Windows およびその他のデスクトップソフトウェアでは、エージェントを初めて起動するときにプロンプトが表示されますが、グループポリシーが原因でこの問題が発生しない場合は、[手動でエントリを追加](#manually-adding-a-firewall-entry)する必要があります。 また、解決する必要がある[プロキシの問題](#proxies)が発生している可能性があります。 |
| Relay | `*.servicebus.windows.net:443`への発信アクセス。 | 企業または個人のネットワークファイアウォールで、このドメインに接続できることを確認します。 また、解決する必要がある[プロキシの問題](#proxies)が発生している可能性があります。|

## <a name="manually-adding-a-firewall-entry"></a>手動によるファイアウォールエントリの追加

前述のように、direct モードでは、パーソナルファイアウォールで、 **vsls エージェント**がポート範囲5990-5999 の接続を受け入れることを許可する必要があります。 Direct モードを使用するが、ファイアウォールに vsls-agent エントリがないことがわかっている場合は、手動で追加することができます。 この方法はファイアウォールソフトウェアによって異なりますが、 **[Windows ファイアウォールの構成](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)** については、こちらを参照してください。

Vsls エージェントのエントリが表示されない場合は、次のいずれかの場所でエージェント実行可能ファイルを見つけることができます。

### <a name="vs-code-agent-location"></a>VS Code エージェントの場所

次のいずれかのパスで、拡張機能のバージョン番号の代わりに**バージョン**を指定します。

- **macOS、Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Visual Studio エージェントの場所

Visual Studio の場所は動的ですが、次の手順に従って実行可能ファイルを見つけることができます。

1. Visual Studio のインストール場所に移動します。 これは通常、**エディション**が Community、Enterprise などの `C:\Program Files (x86)\Microsoft Visual Studio\EDITION`

2. Ide の **拡張機能** サブフォルダーの下にある `vsls-agent.exe` の検索を実行します。

残念ながら、 **Visual Studio Live Share を更新する**たびにこの手順を実行することが必要になる場合があります。

## <a name="proxies"></a>プロキシ

Visual Studio Live Share 現在、プロキシの使用に関していくつかの制限があります。 自動プロキシ設定は Windows で機能しますが、macOS または Linux (および Windows での特定のプロキシ構成) を使用する場合は、 **HTTP_PROXY**環境変数と**HTTPS_PROXY**環境変数を*グローバル*に設定する必要があります。

プロキシでこれらの設定が自動的に行われない場合は、次の形式で手動で変数を設定できます。

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

認証プロキシを使用している場合は、次のようにユーザーとパスワードを追加できます。

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

これらの設定によって問題が解決されない場合は、プロキシの設定の詳細をお知らせください。サポートの改善にご[協力ください](https://github.com/MicrosoftDocs/live-share/issues/86)。

## <a name="see-also"></a>関連項目

- [方法: Visual Studio Code を使用したコラボレーション](../how-to-guides/vscode.md)
- [方法: Visual Studio を使用して共同作業する](../how-to-guides/vs.md)
- [Live Share のセキュリティ機能](security.md)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
