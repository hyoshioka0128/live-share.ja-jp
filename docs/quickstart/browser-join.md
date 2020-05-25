---
title: ブラウザーからの参加-Visual Studio Live Share |Microsoft Docs
description: ブラウザーからの結合の概要
ms.date: 03/18/2020
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: fishah
ms.author: fishah
manager: joncart
ms.workload:
- liveshare
ms.openlocfilehash: 5e485397ff23be0fdab8449fad6237d829775c55
ms.sourcegitcommit: d7f923c1bcd0430b48065ea2c0902b470f530987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83569536"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="preview-joining-a-live-share-session-from-the-browser"></a>✨ [プレビュー] ✨ブラウザーから Live Share セッションに参加する

すべての Live Share コラボレーションセッションは、ブラウザーから参加できるようになりました。 これは、セッションのゲストがセッションに参加するために VS Code または Visual Studio をインストールする必要がなくなったことを意味します。 これは、ユーザーがセッションにすばやくアクセスできるようにする場合や、多くの場合、デスクトップクライアントがインストールされていない学生の場合に、このようなすべてのインスタンスに役立ちます。


# <a name="how-to-join-a-live-share-session-from-the-browser"></a>Live Share セッションをブラウザーから参加させる方法 

### <a name="1-host-starts-session"></a>1. ホスト: セッションを開始します 
最初に、ホストは Visual Studio にアクセスするか、VS Code してコラボレーションセッションを開始する必要があります。 ホストがフォルダーまたはプロジェクトを共有する場合。

![セッションの開始のアニメーション](https://user-images.githubusercontent.com/51928518/76938928-b814e300-68b4-11ea-923e-cefabd4688c6.gif)

### <a name="2-guest-uses-shared-link-to-join-from-browser"></a>2. Guest: 共有リンクを使用してブラウザーから参加する 
Live Share によって、ゲストと共有できる結合リンクが生成されます。 ゲストは、このリンクを使用して web ページに移動できるようになりました。これにより、ブラウザーを続行するオプションが提供されます。

![セッションに参加するアニメーション](https://user-images.githubusercontent.com/51928518/76941137-b8af7880-68b8-11ea-8228-41fdf4afd3ef.gif)

### <a name="3-guest-enjoys-full-fidelity-collaboration-experience-from-browser"></a>3. Guest: ブラウザーから完全な忠実度のコラボレーションエクスペリエンスを利用 
ゲストは、セッションに参加した後、デスクトップクライアントから共同作業している場合と同じように処理できます。

![完全な忠実度のアニメーション](https://user-images.githubusercontent.com/51928518/76942009-40e24d80-68ba-11ea-885c-6eb1069ed550.gif)

<!---
# Frequently asked questions 

##### 1. Is there an environment running in the background, that is hosting my session in the browser?
When you join a Live Share session from the browser, there is no new environment spun up. It is a serverless service. 
##### 2. Do I have to pay for the service of joining from the browser?
Joining from the browser is free, much like all of Live Share.

##### 3. How is this different from Visual Studio Online?
When you join from the browser, you only access the VS Code client from the browser during the session. Once the session ends, all the files and folders along with editor capabilities will close. To use an editor in the browser, backed with your own environment to edit your own files, you must use [Visual Studio Online.](aka.ms/vso)

##### 4. Does this work for all browsers?
Yes. This works on all browsers. 
##### 5. Is there a VS client that I can use in the browser?
We do not have this available yet. 

# Feedback and issues 
This is a preview feature, and we hope to get user feedback to improve the experience. Please fill out any feedback or issues you see on our GitHub repo [here.](https://github.com/MicrosoftDocs/live-share/issues/new?template=bug_report.md)

--->
