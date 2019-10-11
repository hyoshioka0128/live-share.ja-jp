---
title: 存在-Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live Share の連絡先のプレゼンスサービスに関する情報。
ms.custom: ''
ms.date: 10/08/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: fishah
ms.author: fishah
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: c1b3e71578ed3ffb306060cec3354f33423928be
ms.sourcegitcommit: 24eb903744b837dcedff67d8179f06862bd2aa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250670"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="contacts-in-live-share"></a>Live Share の連絡先 

Live Share を使用しており、外部アプリケーション (チャットや電子メールなど) 経由でのリンクの送信が非常に高速になる可能性があることに注意してください。 コラボレーションを促進する場合は、お客様の満足度をできるだけ少なくする必要があります。 これにより、Live Share の**連絡先**に**状態**が含まれるようになりました。

>連絡先は、すべてのバージョンの**Live Share v 1.0.950**以降で自動的に有効になります。

連絡先は、次の図に示すように、別のウィンドウとして Live Share ウィンドウに表示されます。 

![連絡先](../media/vscode-contacts-intro.png)

<em>[Live Share] ウィンドウに [連絡先] ウィンドウが表示される</em>
## <a name="who-shows-up-in-my-contacts"></a>連絡先に表示されるユーザー

[連絡先] ウィンドウには、開発者の自然ワークフローをサポートする2種類の連絡先が表示されます。
### <a name="1-recent-contacts"></a>1. 最近使用した連絡先  
 これらは、以前に Live Share を使用して共同開発した開発者です。 実際には、ほとんどの開発者は同じユーザーと頻繁に共同作業を行うため、最近の一覧により、チームやクラスルームなどをより反復的に扱うことができます。
### <a name="2-suggested-contacts"></a>2. 推奨連絡先
過去30日以内に現在開いているプロジェクトに貢献している開発者です。 実際には、これらは共同作業が必要になる可能性があるため、作業を簡単に開始できるようにするためにお勧めします。

## <a name="direct-user-invitations"></a>ユーザーへの直接招待 
すべての連絡先は、エディター内から Live Share セッションに直接招待できます。これらのユーザーには、セッションに参加するためのオプションを提供するトースト通知が表示されます。 これにより、セッション Url 全体を交換する必要がなくなります。
![DirectInvitationVSCode @ no__t<em>(左側) Live Share は、ピア (right) をセッションに直接招待</em>します。

## <a name="how-does-status-for-contacts-work"></a>連絡先の状態はどのように動作しますか。
開発者が Live Share でサインインすると、**その可用性の状態がそのピアに発行されます。** その結果、チームのメンバーがオンラインになっていることがわかります。その後、前述の直接招待を使用して、共同作業をすぐに開始できます。
状態は、エディター内から直接設定できます。これにより、コンテキストの切り替えを必要とせずに、チームの利用可能性を通知できます。 現在、Live Share の連絡先には次の4つの状態があります。

**1.利用可能:** Live Share 拡張機能を使用していて、セッションに含まれていないときにエディターをアクティブに使用している場合は、既定の状態が 0 @no__t になります。

**2.応答不可:** 現在アクティブな Live Share セッション内にあり、すべての招待通知が抑制されている場合は、状態が `Do not disturb` に設定されます。

**3.退席中:** 5分間非アクティブになると、状態は自動的に `Away` に切り替わります。

**4.Offline:** 長時間にわたって、または[共有状態](##ManagingPresence)を解除することを選択した場合は、オフラインになります。


## 連絡先の管理と状態<a name="ManagingPresence"></a>の共有

この機能を無効にする場合は、次の2つの方法で選択できます。
1. @No__t-0 にすることを選択して、状態設定を無効にすることができます。 無効にすると、他の状態を確認して招待することができますが、自分の状態は発行されず、他のユーザーが直接招待することはできません。
[状態] 円をクリックすると、次のドロップダウンメニューが表示され、オフラインにすることができます。

![dropdownstatus @ no__t-1 (<em>プレゼンスの状態のドロップダウンを示す</em>)

2. @No__t-0 を開き、*Extensions > Visual Studio Live Share > Live Share にアクセスできます。存在 @ no__t-0 とプレゼンスサービスを無効にします。 無効にすると、他の状態を確認して招待することができますが、自分の状態は発行されず、他のユーザーが直接招待することはできません。

![presencesettings](../media/vscode-presence-setting.png)

## <a name="faqs"></a>FAQ 

###### <a name="1-will-i-be-automatically-opting-into-sharing-status-when-i-use-live-share-v10950-and-above"></a>1. Live Share v 1.0.950 以上を使用すると、状態の共有が自動的に解除されますか?

初めて連絡先を表示したときに、トーストが通知され、状態を共有するためのオプションが表示されます。 その後、前に示したようにオプトアウトを選択しない限り、自分の連絡先との状態が自動的に共有されます。

###### <a name="2-can-i-add-my-own-contacts"></a>2. 自分の連絡先を追加できますか。

現在、連絡先サービスでは、同時にコードを共有したり作業したりする同僚を自動的に検出し、独自の連絡先を追加することはできません。 


>手動で連絡先を追加できると思いますか。 GitHub 機能の要求をここで開くことで、これに優先順位を付けることができ[ます。](https://github.com/MicrosoftDocs/live-share/issues/new?template=feature_request.md)
 

 