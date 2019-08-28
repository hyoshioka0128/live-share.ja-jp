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
ms.openlocfilehash: 04bfb314ebae711566a8bab8b0ada8f2fbd2e940
ms.sourcegitcommit: 6b46e300d76eda661ab34c67a3b909d5c162cd9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "70062287"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>インサイダー

Visual Studio Live Share チームは、迅速に反復処理し、新しいアイデアを試し、顧客をリッスンすることに関するものです。 内部関係者は、すべての新機能を最初に試して、お客様の貴重なフィードバックを提供する機会をユーザーに提供します。 以下の内部者に[なる](#BecomeanInsider)方法について説明し、開発者による共同作業の計画を支援します。 

## <a name="new-to-insiders"></a>内部関係者に新しい✨✨


### <a name="reusable-sessions-vs-code"></a>**再利用可能なセッション (VS Code)**

Live Share は再利用可能なセッションをホストできるようになりました。 再利用可能なセッションを使用すると、さまざまなシナリオで Live Share セッションを再利用できます。これは、技術的なインタビュー、毎週の mob セッション、友人の指導中に同じセッションを使用して、さらに多くのことを行うために、Live Share セッションを事前にスケジュールできることを意味します。

再利用可能なセッションを作成するには、次の手順を実行します。
1. を使用し`Command Palette`てにアクセスします。`Ctrl+Shift+P`
1. 「Live Sha...」と入力します。次に、 **_Live Share をクリックします。再利用可能な_セッションリンク**の作成コマンド。

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. これにより、再利用可能なセッションが作成され、それに対するリンクがクリップボードにコピーされます。 エディターの右下隅に通知のポップアップが表示されます。

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. 再利用可能なセッションが作成されました。 セッションの合致とリンクを共有し、セッションにアクセスするたびに使用します。

> [!TIP] 
>再利用可能なセッションリンクは永続的であり、作成日から30日、または前回の使用日から30日間継続します。 つまり、少なくとも30日ごとにセッションを使用し続けると、期限切れを心配する必要はありません。 簡単にアクセスできる安全な場所にリンクを保存するだけです。
 

### <a name="direct-user-invitations"></a>**ユーザーへの直接招待**

現時点では、次の2つの`Contacts`主要な機能を有効にするペインが Visual Studio と Visual Studio Code の両方に用意されています。

1. の`Suggested Contacts`一覧を表示します。これは、過去30日以内に現在開いているプロジェクトに貢献している開発者です。 実際には、これらは共同作業が必要になる可能性があるため、作業を簡単に開始できるようにするためにお勧めします。

2. の`Recent Contacts`一覧を提供します。これは、以前に Live Share を使用した開発者です。 実際には、ほとんどの開発者は同じユーザーと頻繁に共同作業を行うため、最近の一覧により、チームやクラスルームなどをより反復的に扱うことができます。

ただし、現在`Contacts`の一覧では、最近の連絡先を電子メールで招待することのみが許可されています。これは、これまでにないほど効率的ではありません。 最新の Live Share 更新プログラムをインストールして ( `Insiders`前述のように) 有効にすると、**開発者を IDE から直接コラボレーションセッションに招待**できるようになります。 Visual Studio Code を使用する場合は、この機能を使用するために、 [Insider ビルド](https://code.visualstudio.com/insiders/)をインストールする必要があることに注意してください。

![直接 Invitatiosn](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>Live Share ホスト (左側) は、ピア (right) をセッションに直接招待します。</em>

開発者が Live Share でサインインすると、その可用性の状態がそのピアに発行されます。 その結果、チームのメンバーがオンラインになっていることを確認し、すぐに共同作業を開始できます。 これらのユーザーには、セッションに参加するためのオプションを提供するトースト通知が表示されます。 これにより、セッション Url 全体を交換する必要がなくなります。

非アクティブな状態が5分続くと、状態は`Away`自動的にに切り替わり、Live Share セッション内では、状態が自動的に ( `Do not disturb` suprresses 招待トースト通知) に切り替わります。 再びアクティブになったり、Live Share セッションを終了したりすると、状態は自動的にに`Available`戻ります。 この動作により、Live Share の状態を実際に管理する必要はありません。 直接招待を有効にするだけで、共同作業に使用できるかどうかに関係なく、同僚と通信することができます。 ただし、必要に応じていつでも手動で状態を設定できます。

この機能を無効にする場合は、Visual Studio の Live Share 設定と Visual Studio Code `Presence`で設定を無効にするだけです。 無効にすると、他の状態を確認して招待することができますが、自分の状態は発行されず、他のユーザーが直接招待することはできません。

 

## Insider <a name="BecomeanInsider"></a>になる

既定では、Visual Studio Live Share 拡張機能をインストールした後、 `Stable`機能セットを使用しています。これには、すべての実稼働対応機能 (共同編集、共有デバッグ、ターミナルなど) が含まれます。 ただし、作業中の機能にすぐにアクセスできるようにするには、IDE で次の設定を変更`Insiders`して、機能セットを選択します。

* Visual Studio

    ![機能セット-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![機能セット-vscode](../media/feature-set-vscode.png)

以下のセクションでは、現在`Insiders`機能セット内にある一連の機能について説明します。したがって、前述の設定を変更した後で評価することができます。



## <a name="see-also"></a>関連項目

- [言語とプラットフォームのサポート](platform-support.md)
- [Live Share の接続要件](connectivity.md)
- [Live Share のセキュリティ機能](security.md)
- [すべての主要なバグ、機能要求、および制限事項](https://aka.ms/vsls-issues)
- [すべての機能要求および制限事項](https://aka.ms/vsls-feature-requests)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
