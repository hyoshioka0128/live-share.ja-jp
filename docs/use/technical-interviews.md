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
ms.openlocfilehash: db2365b92f5b18198a2f976e1c6ce3d5abb755c5
ms.sourcegitcommit: d7f923c1bcd0430b48065ea2c0902b470f530987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83569523"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>方法: Live Share を使用して技術的なインタビューを行う

インタビューに Live Share を使用すると、インタビューアーと候補者は、完全に忠実な IDE またはエディターを使用して、高速で信頼性の高いインタビューセッションを行うことができます。 


## <a name="setup-for-interviewer"></a>インタビューアーのセットアップ 
Live Share で候補にインタビューするには、次の2つのデスクトップクライアントのいずれかを最初に行う必要があります。

Live Share 拡張機能を使用してビルドされた[Visual Studio](../use/vs.md)をインストールする

>[!TIP] 
> Live Share に対して、 *[ツール] [> オプション] > Live Share > 高度な > 機能]* の順に移動して、insider をオンにしてください。 これにより、組み込みのオーディオ通話サポートを使用してインタビューを行うことができます。

または、 [Visual Studio Code](../use/vscode.md)をインストールして、marketplace から[Live Share 拡張機能パック](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack)をダウンロードします。 拡張機能パックは、インタビューに関するオーディオサポートを提供します。 

## <a name="scheduling-an-interview"></a>インタビューのスケジュール設定 

**VS Code の Live Share**には、事前に Live Share セッションを作成する機能が用意されています。 セッションを事前に作成するには、次の手順を実行します。

1. を使用してにアクセスします。 `Command Palette``Ctrl+Shift+P`
1. 「Live Sha...」と入力します。[_Live Share: 再利用可能なセッションリンクの作成_] コマンドをクリックします。

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. これにより、再利用可能なセッションが作成され、それに対するリンクがクリップボードにコピーされます。 エディターの右下隅に通知のポップアップが表示されます。

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. リンクを送信します。

このリンクを作成したら、電子メールまたは選択したスケジュールメカニズムを使用して、interviewee と共有するだけです。 インタビュー時にそのリンクをクリックするだけで、Live Share セッションに含まれるようになります。 
> [!TIP] 
>再利用可能なセッションリンクは永続的であり、作成日から30日、または前回の使用日から30日間継続します。 インタビュー用の再利用可能なセッションリンクを生成するときに、インタビューがリンクの作成日から30日以内であることを確認します。 リンクの有効期限が切れた場合は、新しい再利用可能なセッションを作成します。 (リンクが決して期限切れにならないようにする方法はありますが、これは簡単にインタビューできます)。

**注:** 現在、Visual Studio の Live Share には、事前にセッションを作成する機能はありません。 Visual Studio で Live Share を使用してインタビューを行う場合は、こちらのガイドに従って、ここで簡単な Live Share セッションを開始する方法に関するガイドを参照して[ください](../quickstart/share.md)。



## <a name="setup-for-candidate"></a>候補のセットアップ
候補は、いつでも Visual Studio または Visual Studio Code をインストールしてインタビューに参加することができますが、これを行う必要はありません。 **Live Share のインタビューセッションは、前のセットアップなしで候補として参加させることができます。** セッションの時点で面接リンクをクリックし、**ブラウザーから参加**することができます。 詳細について[は、こちらをご覧ください。](../quickstart/browser-join.md)



<!--
### **What to do as an Interviewer?**

As an interviewer you will act as the host of the Live Share session. If you are not familiar with Live Share, we suggest you refer to the [share a project](../use/vscode.md) section of our how-to guide
### **What to do as the Interviewee?**

If you are expecting to do a Technical Interview using Live Share, you are in luck! We want to make sure you are familiar with the basic Live Share features so you feel comfortable during your interview.

1. Before the interview, take some time and look over the [How-to guide](../use/vscode.md) so you understand how Live Share works.

1. You may want to install Visual Studio Code beforehand so that you are not waiting for the installation to complete once you start your interview

1. If you don't have the time, no worries. All you need to have a full interview is the link to a Live Share session your interviewer sends you while scheduling the interview. Just clicking on the link will automatically take you through all the steps needed.

1. At the time of the interview, just click on the link and follow the steps it takes you through. If you are early or your interviewer is late to the interview, don't worry! You will just be in the 'lobby' waiting for your interviewer to join. No other steps are required, and once your interviewer joins the session will automatically start.

>[!NOTE]
>If you find that the session has disconnected before or after the interviewer joined, don't worry. Just exit out of that session if (it isn't already closed) and re-click on the same link!

You are now all set to go with using Live Share for your interview! 
-->
