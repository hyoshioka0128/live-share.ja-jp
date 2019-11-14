---
title: 手動参加-Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live share でコラボレーションセッションを手動で参加させる方法について説明します。
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
ms.openlocfilehash: 0d46cb53a28bfac1c088371ff5eecdb6af0c8420
ms.sourcegitcommit: 3a1b22eac528b0f6a241f9fec7ec20264db24cfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2019
ms.locfileid: "74019790"
---
# <a name="join-a-session-manually"></a>セッションに手動で参加する

コラボレーションセッションに参加するために、ブラウザーでリンクを開くだけでなく、既に実行中のツールにリンクを貼り付けることによって、手動で参加させることができます。 これは、通常とは異なるツールを使用する場合や、何らかの理由で、招待リンクの取得に問題がある場合に便利です。

正確な手順は[Visual Studio](#join-from-visual-studio)と[Visual Studio Code](#join-from-visual-studio-code)によって異なります。そのため、詳細については、使用するツールを選択してください。

## <a name="join-from-visual-studio-code"></a>Visual Studio Code からの結合

### <a name="1-sign-in"></a>1. サインイン

>**注:** コラボレーションセッションを読み取り専用の guesasdsat として参加させる場合は、サインインをスキップできます。 共有されているが編集できないコードを表示および移動するためのアクセス権があります。

![Web ブラウザーを使用してサインインを求めるトースト通知](../media/vscode-sign-in-toast.png)

共同作業するためには、他のすべてのユーザーに認識されるように、Visual Studio Live Share にサインインする必要があります。 ステータスバーの [Live Share] を**クリック**するか、 **Ctrl + shift + p/Cmd + shift + p**キーを押して、"Live Share: ブラウザーでのサインイン" コマンドを選択します。

![VS Code のサインイン ボタン](../media/vscode-sign-in-button.png)

サインインを求める通知が表示されている間、ブラウザーが起動します。 ブラウザーでのサインイン プロセスが完了したら、ブラウザーを閉じるだけです。

成功したサインインを選択せずに VS Code の問題が発生した場合は、ブラウザーの [成功] 画面にある [問題がある] リンクをクリックし、指示に従います。 詳細については、「[トラブルシューティング](../troubleshooting.md#sign-in)」を参照してください。

### <a name="2-use-the-join-command"></a>2. join コマンドを使用する

VS Code アクティビティバーで Live Share viewlet を開き、[コラボレーションセッションに参加...] を選択します。アイコンまたはエントリ。

![参加 Viewlet アイコン](../media/vscode-join-viewlet.png)

>**注:** 読み取り専用のゲストとして参加している場合は、セッションで参加者を識別するのに役立つ表示名を入力するように求められます。

### <a name="3-paste-the-invite-link"></a>3. 招待のリンクを貼り付けます。

送信した招待 URL を貼り付けて、確認のために Enter キーを押します。

これで完了です。 すぐにコラボレーション セッションに接続されるはずです。

## <a name="join-from-visual-studio"></a>Visual Studio からの参加

### <a name="1-sign-in"></a>1. サインイン

インストールが完了したら、Visual Studio を起動してサインインします (まだサインインしていない場合)。 [個人用設定アカウント](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)よりも Visual Studio 用の別のサインインを使用する必要がある場合は、[**ツール] &gt; [オプション] &gt; Live Share &gt; ユーザーアカウント**]にアクセスしてください。

![VS サインイン](../media/vs-sign-in-button.png)

まだ問題が解決していませんか? 「[トラブルシューティング](../troubleshooting.md#sign-in)」を参照してください。

### <a name="2-use-the-join-command"></a>2. join コマンドを使用する

[ファイル] > にアクセスして**コラボレーションセッションに参加**するだけです。

![VS 参加メニュー](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3. 招待のリンクを貼り付けます。

送信した招待 URL を貼り付けて、確認のために Enter キーを押します。

これで完了です。 すぐにコラボレーション セッションに接続されるはずです。

## <a name="see-also"></a>関連項目

クイックスタート

- [クイックスタート: 最初のプロジェクトを共有する](../quickstart/share.md)
- [クイックスタート: 初めてのセッションに参加する](../quickstart/join.md)

方法

- [方法: Visual Studio Code を使用したコラボレーション](../use/vscode.md)
- [方法: Visual Studio を使用して共同作業する](../use/vs.md)
- [方法: フィードバックを提供する](../support.md)

辞書／辞典／その他

- [Live Share の接続要件](connectivity.md)
- [Live Share のセキュリティ機能](security.md)
- [Linux インストールの詳細](linux.md)
- [言語とプラットフォームのサポート](platform-support.md)
- [拡張機能のサポート](extensions.md)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
