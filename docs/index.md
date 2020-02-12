---
title: 概要 - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share とその機能の概要です。
ms.custom: ''
ms.date: 10/30/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: fubaduba
ms.author: fubaduba
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 10679c4ef44e2bdaeb4d8a8f25107b10b5f52243
ms.sourcegitcommit: c2ff6f29393990e91390875bb065bb811c071353
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "76978902"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>Visual Studio Live Share とは

Visual Studio Live Share へようこそ。 Live Share では、使っているプログラミング言語や構築しているアプリの種類に関係なく、リアルタイムで他のユーザーと共同で編集やデバッグができます。 現在のプロジェクトを瞬時に安全に共有したり、共同でデバッグ セッションを開始したり、ターミナル インスタンスを共有したり、localhost の Web アプリを転送したり、音声通話などを行うことができます。

 従来のペア プログラミングとは異なり、開発者は Visual Studio Live Share で、各自の好みのエディター設定 (テーマ、キー バインドなど) を維持しながら、独自のカーソルを持ち連携することができます。 これにより、次から次へとシームレスに移行し、独自にアイデアやタスクを調べることができます。 この共同作業をしながら独立性を保てる機能により、_実際会って行う_コラボレーションのようなエクスペリエンスが得られます。

開始する準備はできましたか。 この記事では、いくつかの概念と必要な拡張機能のインストール方法について説明します。 簡略化されたバージョンをお探しの場合は、[共有](quickstart/share.md)と[参加](quickstart/join.md)に関するクイック スタートをご覧ください。

> [!TIP]
> "*独自のコラボレーション セッションに参加*" できることをご存知でしたか。 これを使うと、Live Share を独自に試したり、Visual Studio または VS Code のインスタンスを起動してリモートでそれに接続したりできます。 両方のインスタンスで同じ ID を使用することもできます。 ぜひお試しください。

## <a name="install-visual-studio-live-share"></a>Visual Studio Live Share をインストールする

開始する前に、Live Share のコア要件を満たす Visual Studio または Visual Studio Code のバージョンがインストールされていることを確認する必要があります。

- **Visual Studio Code 1.22.0 以上** - Windows 7、8.1、または 10、macOS " *(High Sierra 10.13 以上のみ)* "、64 ビット Linux " *(64 ビット Ubuntu Desktop 16.04 以上、Fedora 27 以上が推奨されます - [詳細情報](use/vscode.md#installation))* "。
- **Visual Studio 2019** (任意のエディション) - Windows 7、8.1、または 10。
- **Visual Studio 2017 15.6 以上** (任意のエディション) - Windows 7、8.1、または 10。

その後は、Visual Studio Live Share 拡張機能を簡単にダウンロードしてインストールできます。

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0+)</strong><br />
        1. Windows (7、8.1、または 10)、macOS <b>(High Sierra 10.13 以上)</b>、64 ビット Linux <b>(<a href="use/vscode.md#installation">詳細</a>)</b> 用の <a href="https://code.visualstudio.com/">Visual Studio Code</a> をインストールします<br />
        2. マーケットプレースから Visual Studio Live Share 拡張機能をダウンロードしてインストールします。 <br />
        3. 再度読み込み、依存関係がダウンロードおよびインストールされるまで待機します (ステータス バーを参照)。<br />
        4. <strong>Linux</strong>:<a href="reference/linux.md#install-linux-prerequisites">ライブラリのインストール</a>を求められた場合は、インストールをクリックし、パスワードを入力して、完了したら VS Code を再起動します。<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1.<a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a> をインストールします。<br/>
        2.<a href="reference/platform-support.md">サポートされているワークロード</a>をインストールします。 (例: ASP.NET、.NET Core、C++、Python、Node.js)<br />
        3. Visual Studio Live Share は、既定でこれらのワークロードと共にインストールされます。 <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 以上</strong><br />
        1. 最新バージョンの <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a> (15.6+) を Windows (7、8.1、または 10) にインストールします。<br/>
        2.<a href="reference/platform-support.md">サポートされているワークロード</a>をインストールします。 (例: ASP.NET、.NET Core、C++、Node.js)<br />
        3. マーケットプレースから Visual Studio Live Share 拡張機能をダウンロードしてインストールします。 <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Visual Studio Live Share をダウンロードして使用すると、[ライセンス条項](https://aka.ms/vsls-license)と[プライバシーに関する声明](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)に同意したものと見なされます。 問題が発生した場合は、[トラブルシューティング](troubleshooting.md)に関するページをご覧ください。

必要な作業は以上です。 これで、VS Code の左下にサインイン状態のバーが、Visual Studio の右上に共有ボタンが表示されるようになりました。 次の作業については、ドキュメントの残りの部分をご覧ください。


## <a name="see-also"></a>関連項目

クイックスタート

- [最初のプロジェクトを共有する](quickstart/share.md)
- [最初のセッションに参加する](quickstart/join.md)

方法

- [Visual Studio Code を使用して共同作業する](use/vscode.md)
- [Visual Studio を使用して共同作業する](use/vs.md)

参照

- [Live Share の接続要件](reference/connectivity.md)
- [Live Share のセキュリティ機能](reference/security.md)
- [言語とプラットフォームのサポート](reference/platform-support.md)
- [拡張機能のサポート](reference/extensions.md)
- [リリース ノート](https://aka.ms/vsls-releases)

問題が発生していますか? [トラブルシューティング](troubleshooting.md)または[フィードバックの送信](support.md)に関するページをご覧ください。
