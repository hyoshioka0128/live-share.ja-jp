---
title: ブラウザーからの参加-Visual Studio Live Share |Microsoft Docs
description: その browser からの結合の概要
ms.date: 03/18/2020
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: fishah
ms.author: fishah
manager: joncart
ms.workload:
- liveshare
ms.openlocfilehash: 741292a3df8b86a8f7a9484875b352ebe6e8ec10
ms.sourcegitcommit: 382f069abbd81ed258d497a974b30379be36b4f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "79510637"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="preview-joining-a-live-share-session-from-the-browser"></a>✨ [プレビュー] ✨ブラウザーから Live Share セッションに参加する

すべての Live Share コラボレーションセッションで、ブラウザーから参加できるようになりました。 これは、セッションのゲストがセッションに参加するために VS Code または Visual Studio をインストールする必要がなくなったことを意味します。 これは、ユーザーがセッションにすばやくアクセスできるようにする場合や、多くの場合、デスクトップクライアントがインストールされていない学生の場合に、このようなすべてのインスタンスに役立ちます。

> [!TIP]
> ブラウザーからの参加に関してよく寄せられる質問については、以下の FAQ セクションをご覧ください。

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
# <a name="frequently-asked-questions"></a>よく寄せられる質問 

##### <a name="1-is-there-an-environment-running-in-the-background-that-is-hosting-my-session-in-the-browser"></a>1. バックグラウンドで実行されている環境は、ブラウザーでセッションをホストしていますか。
ブラウザーから Live Share セッションに参加すると、新しい環境はスピンアップされません。 サーバーレスサービスです。 
##### <a name="2-do-i-have-to-pay-for-the-service-of-joining-from-the-browser"></a>2. ブラウザーからの参加サービスに対して料金を支払う必要がありますか。
すべての Live Share のように、ブラウザーからの参加は無料です。

##### <a name="3-how-is-this-different-from-visual-studio-online"></a>3. Visual Studio Online との違いについて教えてください。
ブラウザーから参加する場合は、セッション中にブラウザーからのみ VS Code クライアントにアクセスします。 セッションが終了すると、すべてのファイルとフォルダーがエディター機能と共に終了します。 ブラウザーでエディターを使用して独自のファイルを編集するには、 [Visual Studio Online](aka.ms/vso)を使用する必要があります。

##### <a name="4-does-this-work-for-all-browsers"></a>4. これはすべてのブラウザーで機能しますか。
はい。 これはすべてのブラウザーで機能します。 
##### <a name="5-is-there-a-vs-client-that-i-can-use-in-the-browser"></a>5. ブラウザーで使用できる VS クライアントがあるかどうか。
これはまだ利用できません。 

# <a name="feedback-and-issues"></a>フィードバックと問題 
これはプレビュー機能であり、エクスペリエンスを向上させるためにユーザーからのフィードバックを得ることをお勧めします。 GitHub リポジトリに表示されるフィードバックや問題については、こちらを参照してください[。](https://github.com/MicrosoftDocs/live-share/issues/new?template=bug_report.md)