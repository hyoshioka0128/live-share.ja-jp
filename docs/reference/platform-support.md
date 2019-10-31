---
title: プラットフォームと言語のサポート-Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live share のプラットフォームと言語のサポートの概要を説明します。
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 386a8204787ed378413e1b35b7c2a80e0de678ce
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170092"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>言語とプラットフォームのサポート

Visual Studio Live Share の機能は、さまざまな言語およびアプリケーションプラットフォームで動作することを目的としています。 ただし、バリエーションの数が非常に多い場合は、一部のプラットフォームと言語の方が他よりも完成しています。 このドキュメントでは、現在サポートされている機能について、多くの一般的な言語とプラットフォームの現在の既知の状態について説明します。

必要な言語またはプラットフォームをご覧ください。 表示されないものを追加しますか? [ここに投票してください。](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

すべての言語/プラットフォームには、同じファイル intellisense (それぞれの拡張機能がインストールされている場合)、および色付けと共同編集のサポートがあります。 次の一覧では、現在完全なユニバーサルサポートなしで現在の高度な機能について説明しています。

### <a name="languages"></a>言語

| 言語 | 共有言語サービス | 共有デバッグ |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *該当なし* |
| ボール | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | *N/A* <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | *N/A* <sup>4</sup> |
| [水晶](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | *N/A* <sup>4</sup> |
| CSHTML | *該当なし* <sup>1</sup> | ✅ |
| CSS | *該当なし* | *該当なし* |
| Dart | ✅ | ✅ |
| Docker | ✅ | *該当なし* |
| 登録 xir | ✅ | ✅ |
| 同 | ✅ |  *N/A* <sup>4</sup> |
| Erlang | ✅ | ✅ |
| F# | ✅ |  *N/A* <sup>4</sup> |
| [フロー] | ✅ |  *N/A* <sup>4</sup> |
| Fortran | ✅ | *該当なし* |
| 移動 | ✅ | ✅ |
| Gradle | ✅ | *N/A* <sup>4</sup> |
| GraphQL | ✅ | *N/A* <sup>4</sup> |
| Haskell | ✅ | ✅ |
| HTML | *該当なし* | <sup>2</sup> |
| Java | ✅ | ✅ |
| JavaScript/TypeScript | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | *N/A* <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *該当なし* | *N/A* <sup>4</sup> |
| Lua | ✅ | ✅ |
| Markdown | ✅ | *該当なし* |
| MATLAB |  ✅ | *N/A* <sup>4</sup> |
| Objective-C | ✅ | *N/A* <sup>4</sup> |
| Pascal | ✅ | *N/A* <sup>4</sup> |
| Perl | ✅ | ✅ |
| PHP | ✅ | ✅ |
| PowerShell | *該当なし* | ✅ |
| Python |  ✅ | ✅ |
| PureScript | ✅ | *N/A* <sup>4</sup> |
| R |  ✅ | *N/A* <sup>4</sup> |
| [理由/OCaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | *N/A* <sup>4</sup> |
| reStructuredText | ✅ | *該当なし* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | *N/A* <sup>4</sup> |
| [Sass](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *該当なし* |
| Scala | ✅ | *N/A* <sup>4</sup> |
| Solidity | ✅ | *N/A* <sup>4</sup> |
| SQL/T-SQL | *該当なし* | *N/A* <sup>4</sup> |
| [感知](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *該当なし* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *N/A* <sup>4</sup> |
| Swift | ✅ | *N/A* <sup>4</sup> |
| Terraform | ✅ | *N/A* <sup>4</sup> |
| XML | ✅ | *N/A* <sup>4</sup> |
| YAML | ✅ | *N/A* <sup>4</sup> |

<sup>1</sup>拡張での CSHTML C#のサポートはありません。<br />
<sup>2</sup>クライアントデバッグを実行するときに、HTML の埋め込み JavaScript がサポートされます。<br />
<sup>3</sup>ノードまたはブラウザー用の JavaScript/TypeScript デバッグ。<br />
<sup>4</sup> VS Code のそれぞれの拡張機能は、現在デバッグをサポートしていません。 その後すぐに、共同デバッグサポートを追加することを検討します。 <br />

### <a name="platforms"></a>プラットフォーム

| アプリ/プラットフォームの種類 | 共有デバッグ | アプリの共有 |
|-------------------|--------------|-------------|
| arduino | ✅ | *該当なし* |
| Azure App Service | ✅ | *該当なし* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Azure Functions (ローカルおよびリモート) | ✅ | ✅ <sup>1</sup> |
| ブロックチェーン (Ego Um) | ✅ | ✅ <sup>1</sup> |
| コンソール/CLI | ✅ | ✅ <sup>4</sup> |
| データベース | <sup>5</sup> | ✅ <sup>1</sup> |
| デスクトップ (電子/ネイティブ) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| ゲーム (Unity) | ✅ | <sup>9</sup> |
| ゲーム (Unreal) | ✅ | <sup>9</sup> |
| Kubernetes (YAML、ヘルム) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *該当なし* | ✅ <sup>6</sup> |
| モバイル (Cordova) | ✅ | ✅ <sup>1, 7</sup> |
| モバイル (ネイティブ) | ✅ | <sup>9</sup> |
| モバイル (ネイティブに応答) | ✅ | ✅ <sup>1、8</sup> |
| Web アプリ/API (バックエンド) | ✅ | ✅ <sup>1</sup> |
| Web アプリ (フロントエンド) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| VS Code 拡張機能 | | <sup>9</sup> |

<sup>1</sup> [共有ローカルサーバー](../how-to-guides/vscode.md#share-a-server)経由。<br />
<sup>2</sup>デバッグは、ゲストではなくホストのブラウザーに対して行われます。<br />
<sup>3</sup> : バックエンドを共有します。<br />
<sup>4</sup>共有端末でサポートされています。<br />
<sup>5</sup>データベースストアドプロシージャのデバッグは現在サポートされていません <br />
<sup>6</sup> "preview" を使用します。 ただし、既知の問題のために画像が表示されることはありません。 [ここで投票 (👍) します。](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> Cordova アプリは "ブラウザー" プラットフォームを介して共有できます。<br />
<sup>8</sup>応答のネイティブアプリは、エキスポと[共有サーバー](../how-to-guides/vscode.md#share-a-server)を介して共有できます。<br />
<sup>9</sup> Live Share は、現在、windows/画面の共有をサポートしていません。 [ここで投票 (👍) します。](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Visual Studio

ほとんどの言語では1つのファイル Intellisense がサポートされていますが、次に示すいくつかの注意事項があります。 すべての言語/プラットフォームは共同編集をサポートしています。 この一覧の残りの部分では、現在完全なユニバーサルサポートなしで、現在の高度な機能について説明します。

### <a name="languages"></a>言語

| 言語 | 単一ファイル言語サービス | プロジェクト全体の言語サービス | 共同デバッグ |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅<sup>1</sup> | | ✅ |
| .ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *該当なし* | <sup>2</sup> |
| CSS | ✅ | *該当なし* | *該当なし* |
| JavaScript/TypeScript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *該当なし* | *該当なし* |
| PowerShell | ✅ | *該当なし* | ✅ |
| VB.NET | ✅ | | ✅ |
| .VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *該当なし* | <sup>4</sup> |
| SQL/T-SQL | ✅ | *該当なし* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *該当なし* | ✅ |

<sup>1</sup>ギャップ: CSHTML、VBHTML、および ASPX は、embedded C#/vb のサポートC#に関する既知の問題を示していますが、intellisense が実装されていないため、intellisense ファイルは解決されません。 [ここでは、CSHTML/VBHTML で投票 (👍) します。](https://github.com/MicrosoftDocs/live-share/issues/59) [ここでは、ASPX で投票 (👍) します。](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup>クライアントデバッグを実行するときに、HTML の埋め込み JavaScript がサポートされます。<br />
<sup>3</sup>ノードまたはブラウザー用の JavaScript/TypeScript デバッグ。<br />
<sup>4</sup> : XAML 自体のデバッグは、技術的には N/A ですが、コードビハインドのデバッグはサポートされています。<br />
<sup>5 つ</sup>のギャップ: R 言語サービスエラーが発生した場合のゲスト側でのすべての改行の後。 サポートされていません。 [ここで投票 (👍) します。](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>プラットフォーム

| アプリ/プラットフォームの種類 | 共同デバッグ | アプリの共有 |
|-------------------|--------------|-------------|
| Web アプリ/API (バックエンド) | ✅ | ✅ <sup>1</sup> |
| Web アプリ (フロントエンド) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Azure Functions | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Azure Dev Spaces](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| データベース | <sup>4</sup> | ✅ <sup>5</sup> |
| コンソール/CLI | ✅ | ✅ <sup>6</sup> |
| デスクトップ (WinForms) | ✅ | |
| デスクトップ (WPF) | ✅ | |
| ユニバーサル Windows プラットフォーム | ✅ |  |
| VS 拡張機能 | ✅ |  |

<sup>1</sup> [共有ローカルサーバー](../how-to-guides/vs.md#share-a-server)経由。 ASP.NET Web Apps では、 [Web アプリの自動共有](../how-to-guides/vs.md#automatic-web-app-sharing)を使用することもできます。<br />
<sup>2</sup>デバッグは、ゲストではなくホストのブラウザーに対して行われます。<br />
<sup>3</sup> : バックエンドを共有します。<br />
<sup>4</sup>データベースストアドプロシージャのデバッグは現在サポートされていません <br />
<sup>5</sup> ([共有ローカルサーバー](../how-to-guides/vs.md#share-a-server)経由) <br />
<sup>6</sup>共有端末で部分的にサポートされています。<br />
<sup>?</sup> まだ検証されていません。

## <a name="see-also"></a>関連項目

- [拡張機能のサポート](extensions.md)
- [Live Share の接続要件](connectivity.md)
- [Live Share のセキュリティ機能](security.md)
- [すべての主要なバグ、機能要求、および制限事項](https://aka.ms/vsls-issues)
- [すべての機能要求および制限事項](https://aka.ms/vsls-feature-requests)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
