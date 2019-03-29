---
title: 手動結合 - Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live で共同作業セッションを手動で結合する方法については、次の共有します。
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
ms.openlocfilehash: 8ec4bac1c169c17de5e5ec8d26352cc13d62683b
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640069"
---
# <a name="join-a-session-manually"></a>セッションを手動で結合します。

コラボレーション セッションに参加するブラウザーでリンクを開くだけでなく、既に実行されているツールにリンクを貼り付けることによって手動で参加できます。 これは、通常よりも、または何らかの理由により作業への招待のリンクの取得で問題がある場合は、さまざまなツールを使用する場合に便利だことができます。

正確な手順が異なります[Visual Studio](#join-from-visual-studio)と[Visual Studio Code](#join-from-visual-studio-code)、そのために詳細情報を使用するツールを選択します。

## <a name="join-from-visual-studio-code"></a>Visual Studio Code からの参加します。

### <a name="1-sign-in"></a>1.サインイン

>**注:** 読み取り専用のゲストとして共同作業セッションに参加する場合は、サインインを省略できます。 表示および共有されているコードの前後の移動にアクセスしますが、編集できません。

![Web ブラウザーを使用してサインインを求めるトースト通知](../media/vscode-sign-in-toast.png)

共同作業するためには、他のすべてのユーザーに認識されるように、Visual Studio Live Share にサインインする必要があります。 **クリックして**"Live Share"ステータス バーの項目またはキーを押して [ **Ctrl + Shift + P/Cmd + Shift + P**を選択し、"ライブ共有。Sign In With Browser]\(Live Share: ブラウザーでサインイン\) コマンドを選択します。

![VS Code のサインイン ボタン](../media/vscode-sign-in-button.png)

お使いのブラウザーが、通知が表示されますサインインを求める起動中に起動されます。 ブラウザーでのサインイン プロセスが完了したら、ブラウザーを閉じるだけです。

を実行している VS コードの問題に成功したサインインを取得していない場合、ブラウザーで成功の画面で「問題」リンクをクリックし、指示に従います。 チェック アウト[トラブルシューティング](../troubleshooting.md#sign-in)他のヒント。

### <a name="2-use-the-join-command"></a>2.結合コマンドを使用して、

VS Code アクティビティ バーで、Live Share viewlet を開き、「共同作業セッションに参加してください...」を選択します。アイコンまたはエントリです。

![参加 Viewlet アイコン](../media/vscode-join-viewlet.png)

>**注:** 読み取り専用のゲストとして追加する場合を求められます参加者はセッション内で識別する表示名を入力します。

### <a name="3-paste-the-invite-link"></a>3.招待のリンクを貼り付ける

招待 URL 領域で送信されたことを確認するには、' Enter' キーを貼り付けます。

これで完了です。 すぐにコラボレーション セッションに接続されるはずです。

## <a name="join-from-visual-studio"></a>Visual Studio からの参加します。

### <a name="1-sign-in"></a>1.サインイン

インストールした後は、Visual Studio を起動し、されていないがある場合にサインインします。 も Visual Studio のさまざまなサインインで使用する必要があるかどうか、[パーソナル化アカウント](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)に移動して、**ツール&gt;オプション&gt;Live Share&gt;ユーザー アカウント**します。

![VS をサインインします。](../media/vs-sign-in-button.png)

まだ問題が解決していませんか? 参照してください[トラブルシューティング](../troubleshooting.md#sign-in)します。

### <a name="2-use-the-join-command"></a>2.結合コマンドを使用して、

単に移動して**ファイル > のコラボレーション セッションに参加**します。

![VS 参加メニュー](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3.招待のリンクを貼り付ける

招待 URL 領域で送信されたことを確認するには、' Enter' キーを貼り付けます。

これで完了です。 すぐにコラボレーション セッションに接続されるはずです。

## <a name="see-also"></a>関連項目

クイックスタート

- [クイック スタート:最初のプロジェクトを共有する](../quickstart/share.md)
- [クイック スタート:最初のセッションに参加する](../quickstart/join.md)

方法

- [方法:Visual Studio Code を使用して共同作業する](../use/vscode.md)
- [方法:Visual Studio を使用して共同作業する](../use/vs.md)
- [方法:フィードバックを提供します。](../support.md)

参照

- [Live Share の接続要件](connectivity.md)
- [Live Share のセキュリティ機能](security.md)
- [Linux インストールの詳細](linux.md)
- [言語とプラットフォームのサポート](platform-support.md)
- [拡張機能のサポート](extensions.md)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
