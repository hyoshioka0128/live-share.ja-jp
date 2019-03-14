---
title: 接続 - Visual Studio の Live Share |Microsoft Docs
description: Visual Studio Live Share の接続と接続モードの情報。
ms.custom: ''
ms.date: 03/22/2018
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
ms.openlocfilehash: 6edc5bcf18dde6f84a4972a1efd755592cbef18c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256125"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Live Share の接続要件

この記事では、Visual Studio Live Share、使用可能な接続オプション、および該当する場合の既知の回避策の接続要件をまとめたものです。

## <a name="sign-in"></a>サインイン

Live Share を使用してサインインできます[Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory)バックアップされた職場または学校のアカウントを[Microsoft アカウント](https://account.microsoft.com/account)、または[GitHub プロファイル](https://github.com/)します。 通常、サインイン Url の場合そうでないが、それを使用するパブリックに公開された製品の数を指定されたほとんどの組織で開かれているこれらを開示すること、ネットワーク管理者にお問い合わせください`login.microsoftonline.com`や`github.com`ドメインだけでなく[。以下に示す](#requirements-for-connection-modes)します。

> [!NOTE]
> オンプレミス AD (ADFS) のアカウントと GitHub Enterprise アカウントをオンプレミスで現在サポートされていない[(上向きの矢印に投票👍)](https://github.com/MicrosoftDocs/live-share/issues/341)します。

## <a name="connection-modes"></a>接続モード

最適なことを確認するには、パフォーマンス、既定では Visual Studio Live Share を自動的に検出コラボレーション セッション ホスト マシンとゲスト マシンとのみそれらの間のルートがない場合は、クラウド経由でリレーかどうかをネットワーク経由で直接通信できます。 この混合"auto"モードは柔軟性があり他のユーザーが、同じセッションに対して直接接続するときに、クラウドを介して中継するいくつかのゲストをも可能です。

直接接続は、セキュリティを確保するが、接続を有効にする、5990 ~ 5999 ポートを開く必要がありますにクラウド ベースのメカニズムを使用して認証されます。 その結果、求めることができます、デスクトップのファイアウォールを最初に共有するときに、ポートを開きます。 無視としてオプションを受け入れると、常に自動モードでリレーを使用する Live Share が単に発生します。

Visual Studio Live Share のすべての接続は、ことコラボレーション セッションでのみ、そのコンテンツへのアクセスができることを確認するには、SSH または SSL 暗号化され、中央のサービスに対して認証されます。 さらに、Live Share のクラウド リレーでは、トラフィックを経由してルーティングを無効になるしはない「覗き見」任意の方法でトラフィック。

## <a name="changing-the-connection-mode"></a>接続モードを変更します。

希望する、直接またはリレー型接続を無効にするか、または接続の問題のトラブルシューティングを単に場合は、その他の接続モードを強制できます。

| モード | ホストの動作 | ゲストの動作 |
|------|----------------|----------------------|
| 自動 | ホストの共同作業セッションは、セキュリティで保護された、認証済みの直接接続またはクラウド リレー接続を受け入れます。 | 直接接続を使用しようとして失敗した場合、クラウドを介して中継にフォールバックします。 |
| 直接 | ホストの共同作業セッションは、直接、セキュリティで保護された認証済みの接続のみを受け入れます。 | 直接接続しようとして接続できない場合は停止します。 |
| Relay | ホストの共同作業セッションでは、直接接続は許可されません。 ホストのコンピューター上で開かれているポートはありません。 | 常に、クラウド経由で接続します。 |

モードを変更するには。

**VS:**

1. ツール > オプション > Live 共有します。
2. "接続モード ドロップダウン リストから、モードを選択します。
3. VS を再起動します。

**VS Code:**

1. Settings.json の編集 (ファイル > 設定 > 設定)。
2. 設定`"liveshare.connectionMode"`に`"auto"`、 `"direct"`、または`"relay"`好みに応じて。
3. VS Code を再起動します。

## <a name="requirements-for-connection-modes"></a>接続モードの要件

接続モードでは、特定のポートと関数には、Live Share を使用する必要がある Url が決まります。

| モード | クライアント アクセスの要件 | トラブルシューティング |
|------|--------------|-----------------|
| どれでも可 | 発信アクセス `*.liveshare.vsengsaas.visualstudio.com:443` | 個人のネットワークのファイアウォールでは、このドメインに接続できます。 または、会社の確認をします。 入力 https://insiders.liveshare.vsengsaas.visualstudio.comブラウザーで、Visual Studio Live Share ホーム ページに着陸したことを確認します。 実行しても[プロキシの問題](#proxies)を解決する必要があります。|
| 任意 (VS Code) | 発信アクセス `download.microsoft.com:443` | 個人のネットワークのファイアウォールでは、このドメインに接続できます。 または、会社の確認をします。 実行しても[プロキシの問題](#proxies)を解決する必要があります。 |
| 自動 | 自動スイッチ。 直接参照してくださいとリレーのモード。 | 直接またはリレーをトラブルシューティングするモードに切り替えます。 |
| 直接 | ホスト:ローカル ネットワークの着信接続を受け入れるように開かれている範囲 5990 5999 ニーズを満たすポート。<br /><br />ゲストの場合:ネットワーク ルートと同じポート上のホストへの発信アクセス。 | 「Vsls エージェント」がこのポートの範囲は、デスクトップのファイアウォール ソフトウェアによってブロックされていないと、互いを ping できることを確認します。 Windows およびその他のデスクトップ ソフトウェアように求めるメッセージが最初に、エージェントの起動時、中にインスタンスをグループ ポリシーはこれを防ぐし、する必要があります見てきた[エントリを手動で追加](#manually-adding-a-firewall-entry)します。 実行しても[プロキシの問題](#proxies)を解決する必要があります。 |
| Relay | 発信アクセス`*.servicebus.windows.net:443`します。 | 個人のネットワークのファイアウォールでは、このドメインに接続できます。 または、会社の確認をします。 実行しても[プロキシの問題](#proxies)を解決する必要があります。|

## <a name="manually-adding-a-firewall-entry"></a>ファイアウォールのエントリを手動で追加します。

直接モードは、パーソナル ファイアウォールが許可が必要です、上記のように、 **vsls エージェント**5990 5999 の範囲は、ポートで接続を受け入れるようにします。 直接モードを使用して、、ファイアウォールに vsls エージェントのエントリがないことを見つけた場合は、手動で追加することができます。 この方法は、ファイアウォール ソフトウェアによって異なりますが、に関する情報を得られる**[ここで Windows ファイアウォールを構成する](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)** します。

Vsls エージェントのエントリが表示されない場合、エージェント実行可能ファイルで見つかります、次の場所のいずれか。

### <a name="vs-code-agent-location"></a>VS コードのエージェントの場所

代替**バージョン**下のパスの 1 つの拡張機能のバージョン番号の。

- **macOS、Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Visual Studio エージェントの場所

Visual Studio の場所がより動的には、次の手順を実行、実行可能ファイルを検索することができます。

1. Visual Studio のインストール場所に移動します。 これは通常`C:\Program Files (x86)\Microsoft Visual Studio\EDITION`場所**EDITION** Community、Enterprise などには

2. 検索が実行`vsls-agent.exe`の下で、 **IDE\Extensions**サブ フォルダー。

残念ながら、この手順を実行する必要があります**Visual Studio Live Share を更新するたびにします。**

## <a name="proxies"></a>プロキシ

Visual Studio Live Share は、現在、プロキシの使用方法に関するいくつかの制限を持ちます。 自動プロキシの設定は、macOS または Linux を使用する場合 (および Windows での特定のプロキシ構成を使って)、Windows で機能する必要があります、 **HTTP_PROXY**と**HTTPS_PROXY**環境変数がする必要があります設定する*グローバル*します。

場合は、プロキシでは、これらの設定は自動的に、次の形式で、変数を手動で設定できます。

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

に対して認証プロキシがあれば、することができます、ユーザーとパスワードよう追加します。

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

これらの設定、問題が解決しない場合[ご連絡ください](https://github.com/MicrosoftDocs/live-share/issues/86)プロキシの詳細セットアップのでサポートの向上を見ることができます。

## <a name="see-also"></a>関連項目

- [方法:Visual Studio Code を使用して共同作業します。](../use/vscode.md)
- [方法:Visual Studio を使用して共同作業します。](../use/vs.md)
- [Live Share のセキュリティ機能](security.md)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
