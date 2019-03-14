---
title: プラットフォームと言語のサポート - Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live share プラットフォームと言語のサポートの概要。
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 5c8429779bcfe39842ba298c3b6371daa1cf7fe4
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255939"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>言語とプラットフォームのサポート

Visual Studio Live Share の機能は言語とプラットフォームのアプリケーションの多様な状況で作業を行う対象としています。 ただし、バリエーションの膨大な数を指定するには、いくつかのプラットフォームや言語が他よりも詳細です。 このドキュメントでは、現在の既知のさまざまな一般的な言語とプラットフォームを現在サポートされている機能の状態について説明します。

言語またはプラットフォームが必要ですか。 表示されない 1 つを追加しますか。 [ここで票を投じます。](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

すべての言語やプラットフォームがあると、同じファイルの intellisense (それぞれの拡張機能がインストールされている) 場合などの色づけ共同編集サポート。 現在、完全なユニバーサルのサポートがない場合では高度な機能の下の一覧:

### <a name="languages"></a>言語

| 言語 | 共有言語サービス | デバッグの共有 |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *該当なし* |
| Ballerina | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | *該当なし* <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | *該当なし* <sup>4</sup> |
| [Crystal](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | *該当なし* <sup>4</sup> |
| CSHTML | *該当なし* <sup>1</sup> | ✅ |
| CSS | *該当なし* | *該当なし* |
| Dart | ✅ | ✅ |
| Docker | ✅ | *該当なし* |
| Elixir | ✅ | ✅ |
| Elm | ✅ |  *該当なし* <sup>4</sup> |
| Erlang | ✅ | ✅ |
| F# | ✅ |  *該当なし* <sup>4</sup> |
| [フロー] | ✅ |  *該当なし* <sup>4</sup> |
| Fortran | ✅ | *該当なし* |
| 移動 | ✅ | ✅ |
| Gradle | ✅ | *該当なし* <sup>4</sup> |
| GraphQL | ✅ | *該当なし* <sup>4</sup> |
| Haskell | ✅ | ✅ |
| HTML | *該当なし* | <sup>2</sup> |
| Java | ✅ | ✅ |
| JavaScript / TypeScript | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | *該当なし* <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *該当なし* | *該当なし* <sup>4</sup> |
| Lua | ✅ | ✅ |
| Markdown | ✅ | *該当なし* |
| MATLAB |  ✅ | *該当なし* <sup>4</sup> |
| Objective-C | ✅ | *該当なし* <sup>4</sup> |
| Pascal 形式 | ✅ | *該当なし* <sup>4</sup> |
| Perl | ✅ | ✅ |
| PHP | ✅ | ✅ |
| PowerShell | *該当なし* | ✅ |
| Python |  ✅ | ✅ |
| PureScript | ✅ | *該当なし* <sup>4</sup> |
| R |  ✅ | *該当なし* <sup>4</sup> |
| [理由/OCaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | *該当なし* <sup>4</sup> |
| reStructuredText | ✅ | *該当なし* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | *該当なし* <sup>4</sup> |
| [Sass](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *該当なし* |
| Scala | ✅ | *該当なし* <sup>4</sup> |
| 不透明度 | ✅ | *該当なし* <sup>4</sup> |
| SQL/T-SQL | *該当なし* | *該当なし* <sup>4</sup> |
| [スタイラス](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *該当なし* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *該当なし* <sup>4</sup> |
| Swift | ✅ | *該当なし* <sup>4</sup> |
| Terraform | ✅ | *該当なし* <sup>4</sup> |
| XML | ✅ | *該当なし* <sup>4</sup> |
| YAML | ✅ | *該当なし* <sup>4</sup> |

<sup>1</sup>いいえ CSHTML サポートC#拡張機能。<br />
<sup>2</sup>クライアントのデバッグを行うときに HTML での JavaScript の埋め込みがサポートされています。<br />
<sup>3</sup> JavaScript]/[TypeScript は、ノードまたはブラウザーのデバッグします。<br />
<sup>4</sup> VS Code 用のそれぞれの拡張機能では、デバッグもサポートされていません。 すぐに併置デバッグ サポートの追加調査させていただきます。 <br />

### <a name="platforms"></a>プラットフォーム

| アプリ/プラットフォームの種類 | デバッグの共有 | アプリの共有 |
|-------------------|--------------|-------------|
| Arduino | ✅ | *該当なし* |
| Azure App Service | ✅ | *該当なし* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Azure Functions (ローカルおよびリモート) | ✅ | ✅ <sup>1</sup> |
| ブロック チェーン (Ethereum) | ✅ | ✅ <sup>1</sup> |
| コンソール/CLI | ✅ | ✅ <sup>4</sup> |
| データベース | <sup>5</sup> | ✅ <sup>1</sup> |
| デスクトップ (電子/ネイティブ) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| ゲーム (Unity) | ✅ | <sup>9</sup> |
| ゲーム (Unreal) | ✅ | <sup>9</sup> |
| Kubernetes (YAML、Helm) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *該当なし* | ✅ <sup>6</sup> |
| モバイル (Cordova) | ✅ | ✅ <sup>1,7</sup> |
| モバイル (ネイティブ) | ✅ | <sup>9</sup> |
| モバイル (React ネイティブ) | ✅ | ✅ <sup>1,8</sup> |
| Web app/API (バック エンド) | ✅ | ✅ <sup>1</sup> |
| Web アプリ (フロント エンド) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| VS コード拡張機能 | | <sup>9</sup> |

<sup>1</sup>を介して[ローカル サーバーの共有](../use/vscode.md#share-a-server)します。<br />
<sup>2</sup>デバッグは、ホストのブラウザーではなくゲストに対して発生します。<br />
<sup>3</sup>バック エンドを共有することで。<br />
<sup>4</sup>共有端末でサポートされています。<br />
<sup>5</sup>データベースのストアド プロシージャのデバッグは現在サポートされていません <br />
<sup>6</sup> "preview"を使用しています。 ただし、イメージは、既知の問題によりは表示されません。 [投票 (👍) は、ここです。](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> "browser"プラットフォーム経由で Cordova アプリを共有することができます<br />
<sup>8</sup>エキスポ react Native アプリを共有できると[共有サーバー](../use/vscode.md#share-a-server)します。<br />
<sup>9</sup> live Share では、共有の windows/画面はサポートされていません。 [投票 (👍) は、ここです。](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Visual Studio

ほとんどの言語には、いくつか 1 つのファイルの Intellisense のサポートがありますが、以下に示すいくつかの注意事項があります。 すべての言語/プラットフォームでは、共同編集をサポートします。 一覧の残りの部分では、現在、完全なユニバーサルのサポートがない場合の高度な機能について説明します。

### <a name="languages"></a>言語

| 言語 | 1 つのファイルの言語サービス | プロジェクト全体の言語サービス | 併置のデバッグ |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅  <sup>1</sup> | | ✅ |
| ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *該当なし* | <sup>2</sup> |
| CSS | ✅ | *該当なし* | *該当なし* |
| JavaScript / TypeScript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *該当なし* | *該当なし* |
| PowerShell | ✅ | *該当なし* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *該当なし* | <sup>4</sup> |
| SQL/T-SQL | ✅ | *該当なし* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *該当なし* | ✅ |

<sup>1</sup>ギャップ。CSHTML と VBHTML、ASPX がある既知の問題が約埋め込まれたC#提供される分離コードまたは VB サポートC#または VB のファイルは完全な intellisense が実装されていないために解決されません。 [投票 (👍) こちら CSHTML と VBHTML の。](https://github.com/MicrosoftDocs/live-share/issues/59) [投票 (👍) こちら ASPX の。](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup>クライアントのデバッグを行うときに HTML での JavaScript の埋め込みがサポートされています。<br />
<sup>3</sup> JavaScript]/[TypeScript は、ノードまたはブラウザーのデバッグします。<br />
<sup>4</sup>分離コードのデバッグがサポートされている XAML 自体のデバッグが技術的には該当なし、します。<br />
<sup>5</sup>ギャップ。結合ではすべての改行の後に、ゲスト側で R 言語サービスでエラー。 サポートされていません。 [投票 (👍) は、ここです。](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>プラットフォーム

| アプリ/プラットフォームの種類 | 共同デバッグ | アプリの共有 |
|-------------------|--------------|-------------|
| Web app/API (バック エンド) | ✅ | ✅ <sup>1</sup> |
| Web アプリ (フロント エンド) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Azure Functions  | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Azure 開発のスペース](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| データベース | <sup>4</sup> | ✅ <sup>5</sup> |
| コンソール/CLI | ✅ | ✅ <sup>6</sup> |
| デスクトップ (WinForms) | ✅ | |
| デスクトップ (WPF) | ✅ | |
| ユニバーサル Windows プラットフォーム | ✅ |  |
| VS 拡張機能 | ✅ |  |

<sup>1</sup>を介して[ローカル サーバーの共有](../use/vs.md#share-a-server)します。 ASP.NET Web アプリが使用できるも[自動 web アプリの共有](../use/vs.md#automatic-web-app-sharing)します。<br />
<sup>2</sup>デバッグは、ホストのブラウザーではなくゲストに対して発生します。<br />
<sup>3</sup>バック エンドを共有することで。<br />
<sup>4</sup>データベースのストアド プロシージャのデバッグは現在サポートされていません <br />
<sup>5</sup>を介して[ローカル サーバーの共有](../use/vs.md#share-a-server)します。 <br />
<sup>6</sup>共有端末を使用して部分的にサポートされています。<br />
<sup>?</sup> 検証されていません。

## <a name="see-also"></a>関連項目

- [拡張機能のサポート](extensions.md)
- [Live Share の接続要件](connectivity.md)
- [Live Share のセキュリティ機能](security.md)
- [すべての主要なバグ、機能要求、および制限事項](https://aka.ms/vsls-issues)
- [すべての機能要求や制限事項](https://aka.ms/vsls-feature-requests)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
