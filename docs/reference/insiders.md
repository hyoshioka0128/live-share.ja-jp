---
title: Insider-Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live Share 内の ' Insider ' チャネルの説明。
ms.custom: ''
ms.date: 04/02/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 308f3746bfcdd1f2a428106c1d3e579f49df0cf3
ms.sourcegitcommit: 50069912a317f8685976013e80738bbaa403a3fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72171999"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Insider

Visual Studio Live Share チームは、迅速に反復処理し、新しいアイデアを試し、顧客をリッスンすることに関するものです。 Insider は、すべての新機能を最初に試して、お客様の貴重なフィードバックを提供する機会をユーザーに提供します。 以下の[Insider になる](#BecomeanInsider)方法について説明し、開発者による共同作業の計画を支援します。 

## <a name="new-to-insiders"></a>✨Insider の新機能✨


### <a name="reusable-sessions-vs-code"></a>**再利用可能なセッション (VS Code)**

Live Share は再利用可能なセッションをホストできるようになりました。 再利用可能なセッションを使用すると、さまざまなシナリオで Live Share セッションを再利用できます。これは、技術的なインタビュー、毎週の mob セッション、友人の指導中に同じセッションを使用して、さらに多くのことを行うために、Live Share セッションを事前にスケジュールできることを意味します。

再利用可能なセッションを作成するには、次の手順を実行します。
1. を使用して `Command Palette` にアクセス `Ctrl+Shift+P`
1. 「Live Sha...」と入力します。[ **_Live Share: Create Reusable Session link_** ] コマンドをクリックします。

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. これにより、再利用可能なセッションが作成され、それに対するリンクがクリップボードにコピーされます。 エディターの右下隅に通知のポップアップが表示されます。

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. 再利用可能なセッションが作成されました。 セッションの合致とリンクを共有し、セッションにアクセスするたびに使用します。

> [!TIP] 
>再利用可能なセッションリンクは永続的であり、作成日から30日、または前回の使用日から30日間継続します。 つまり、少なくとも30日ごとにセッションを使用し続けると、期限切れを心配する必要はありません。 簡単にアクセスできる安全な場所にリンクを保存するだけです。
 


## Insider になる<a name="BecomeanInsider"> </a>

既定では、Visual Studio Live Share 拡張機能をインストールした後、`Stable` 機能セットを使用しています。これには、すべての実稼働対応機能 (共同編集、共有デバッグ、ターミナルなど) が含まれます。 ただし、作業中の機能にすぐにアクセスできるようにするには、IDE で次の設定を変更して `Insiders` 機能セットを選択します。

* Visual Studio

    ![機能セット-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![機能セット-vscode](../media/feature-set-vscode.png)

以下のセクションでは、現在 `Insiders` 機能セット内にある一連の機能について説明します。したがって、前述の設定を変更した後で評価することができます。



## <a name="see-also"></a>参照

- [言語とプラットフォームのサポート](platform-support.md)
- [Live Share の接続要件](connectivity.md)
- [Live Share のセキュリティ機能](security.md)
- [すべての主要なバグ、機能要求、および制限事項](https://aka.ms/vsls-issues)
- [すべての機能要求および制限事項](https://aka.ms/vsls-feature-requests)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
