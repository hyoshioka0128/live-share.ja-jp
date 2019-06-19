---
title: Insider - Visual Studio の Live Share |Microsoft Docs
description: Visual Studio Live Share 内の '内部' チャンネルの説明。
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
ms.openlocfilehash: a79effc25c09851301bb2231511a8a9d8a9f549b
ms.sourcegitcommit: 6e84bf17eedd616417f474551344c2161700c4d3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2019
ms.locfileid: "67192721"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>インサイダー

Visual Studio Live Share チームがアドレス ユーザーからのフィードバックに迅速に反復処理しようし、するの一環として、2 つの個別の機能「チャネル」を提供の新機能を受信する速度を決定することができます。 既定では、Visual Studio Live Share の拡張機能をインストールした後を使用する、`Stable`機能セットで、すべての実稼働可能な機能 (例: 共同編集、デバッグ、端末を共有) が含まれています。 ただし、機能に取り組んでいるところにいち早くアクセスを取得する場合は、することができますにオプトイン、`Insiders`お使いの IDE では、次の設定を変更することによって機能します。

* Visual Studio

    ![機能の設定-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![--vscode セット機能](../media/feature-set-vscode.png)

次のセクションでは、現在内にある機能のセットの説明、`Insiders`機能セット、およびそのため、前述の設定を変更すると、評価する準備ができています。

## <a name="direct-user-invitations"></a>ユーザーが直接招待

現時点では、Visual Studio と Visual Studio Code の両方を提供、`Contacts`ウィンドウで、2 つの主要機能を使用します。

1. 一覧を表示する`Suggested Contacts`、過去 30 日以内、現在開いているプロジェクトに関与した開発者であります。 実際には、これらを使用すると、共同作業するチームは、およびそのため、お勧めして開始しやすくためにします。

2. 一覧を提供する`Recent Contacts`、Live Share を使用すると共同で以前した開発者であります。 実際には、ほとんどの開発者が頻繁に同じユーザーと共同作業し、そのため、最近使用した一覧により、チーム、教室などの操作のより反復可能なことを意味します。

ただし、`Contacts`リスト現在のみで、電子メールでまたは提案された最近の連絡先を招待するそれほど効率的ではないを学びました。 最新の共有のライブ更新プログラムをインストールし、有効にする場合`Insiders`(前述)、としてようになりましたことができますを **、IDE から直接、共同作業セッションに開発者を招待**! Visual Studio Code を使用している場合は、インストールする必要あります、 [Insider ビルド](https://code.visualstudio.com/insiders/)でこの機能を使用するためにします。

![直接 Invitatiosn](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>Live Share ホスト (左)、セッションに直接 (右) のピアを招待</em>

開発者のサインイン Live Share を使用すると、可用性の状態は同僚に公開されます。 その結果、チーム内のメンバーがオンラインになりをすぐに開始それらで共同作業を行うことを確認できます。 かどうか、セッションに参加するためのオプションを提供するトースト通知が表示されます。 これには、セッションの Url を完全に交換する必要が削除されます。

アクティブな状態が 5 分後に、状態が自動的に切り替える`Away`、Live Share セッション内でしたら、状態に自動的に切り替えると`Do not disturb`(suprresses 招待トースト通知)。 状態が自動的に切り替わります後、再びアクティブになるや Live Share セッションのままにすると、`Available`します。 この動作では、実際には、Live Share 状態を管理する必要はありません。 これは、単にダイレクトの招待を有効にして、かどうか可能であるコラボレーションかどうかを同僚と通信します。 ただし、したい場合、常に手動で、状態を設定することができます。

単に無効にできますこの機能のオプトアウトする場合、 `Presence` Visual Studio と Visual Studio Code での Live Share 設定内で設定します。 無効にすると、まだできます他のユーザーの状態を確認してユーザーを招待していて、状態は発行されません、他のユーザーが直接ことはできませんと試用版します。

## <a name="see-also"></a>関連項目

- [言語とプラットフォームのサポート](platform-support.md)
- [Live Share の接続要件](connectivity.md)
- [Live Share のセキュリティ機能](security.md)
- [すべての主要なバグ、機能要求、および制限事項](https://aka.ms/vsls-issues)
- [すべての機能要求および制限事項](https://aka.ms/vsls-feature-requests)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
