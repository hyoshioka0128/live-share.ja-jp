---
title: Visual Studio Code を使用して共同作業する - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Code と Live Share のコラボレーションに関する一連のハウツーです。
ms.custom: ''
ms.date: 09/16/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: fubaduba
ms.author: fubaduba
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: 810c60754c0be4f11511fb1ccbb0bb612de42e5d
ms.sourcegitcommit: 3a1b22eac528b0f6a241f9fec7ec20264db24cfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2019
ms.locfileid: "74019833"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>方法: Live Share を使用して技術的なインタビューを行う

技術的なインタビューに Live Share の使用を開始する前に、次の[手順](../use/vscode.md)に従って、 **marketplace からダウンロード Visual Studio Code と Live Share 拡張パックをダウンロード**する必要があります。

Live Share では、再利用可能なセッションをホストすることができます。 これは、技術的なインタビューのために Live Share セッションを事前にスケジュールでき、リンクが期限切れになる心配がないことを意味します。

> [!TIP] 
>再利用可能なセッションリンクは永続的であり、作成日から30日、または前回の使用日から30日間継続します。 インタビュー用の再利用可能なセッションリンクを生成するときに、インタビューがリンクの作成日から30日以内であることを確認します。 リンクの有効期限が切れた場合は、新しい再利用可能なセッションを作成します。 (リンクが決して期限切れにならないようにする方法はありますが、これは簡単にインタビューできます)。

### <a name="what-to-do-as-an-interviewer"></a>**インタビューアーとして何を行うのでしょうか。**

インタビューアーとしては、Live Share セッションのホストとして機能します。 Live Share に慣れていない場合は、「ハウツーガイド」の「[プロジェクトを共有](../use/vscode.md)する」セクションを参照することをお勧めします。

技術的なインタビュー用の Live Share セッションを作成するには、通常のコラボレーションセッションではなく、特別な "再利用可能なセッション" を作成します。 これにより、Live Share のセッションを事前にスケジュールし、いつでも使用できるようになります。

再利用可能なセッションを作成するには、次の手順を実行します。

1. を使用して `Command Palette` にアクセス `Ctrl+Shift+P`
1. 「Live Sha...」と入力します。[ **_Live Share: 再利用可能なセッションリンクの作成_** ] コマンドをクリックします。

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. これにより、再利用可能なセッションが作成され、それに対するリンクがクリップボードにコピーされます。 エディターの右下隅に通知のポップアップが表示されます。

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. 再利用可能なセッションが作成されました。 セッションの合致とリンクを共有し、セッションにアクセスするたびに使用します。

このリンクを作成したら、電子メールまたは選択したスケジュールメカニズムを使用して、interviewee と共有するだけです。 インタビュー時にそのリンクをクリックするだけで、Live Share セッションに含まれるようになります。 

### <a name="what-to-do-as-the-interviewee"></a>**Interviewee として何を行うのでしょうか。**

Live Share を使用して技術的なインタビューを行うことを想定している場合は、運が良ければ、 インタビュー中に快適に使用できるように、基本的な Live Share 機能について理解していることを確認します。

1. インタビューの前に、Live Share のしくみを理解できるように、[操作方法に](../use/vscode.md)ついて説明します。

1. インタビューを開始した後にインストールが完了するのを待たずに、事前に Visual Studio Code をインストールすることもできます。

1. 時間がない場合は、心配はありません。 インタビューのスケジュールを設定しているときに、インタビューアーから送信された Live Share セッションへのリンクが必要なのは、完全なインタビューだけです。 リンクをクリックするだけで、必要なすべての手順が自動的に実行されます。

1. インタビューの時点で、リンクをクリックするだけで、手順に従うことができます。 早い段階で、またはインタビューアーがインタビューに遅れている場合は、心配しないでください。 インタビューアーが参加するのを待機している ' ロビー ' になります。 それ以外の手順は必要ありません。インタビューアーが参加すると、セッションは自動的に開始されます。

>[!NOTE]
>インタビューアーが参加する前または後にセッションが切断されていることがわかった場合は、心配しないでください。 (まだ閉じていない) 場合はそのセッションを終了し、同じリンクを再度クリックします。

これで、インタビューに Live Share を使用するように設定されました。 
