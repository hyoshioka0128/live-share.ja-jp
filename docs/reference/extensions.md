---
title: 拡張機能とエコシステムのサポート - Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live share の拡張機能のサポートの概要。
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
ms.openlocfilehash: 5a9787643643c22ca7302528dc794480d09df902
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256032"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="extensions-and-ecosystem-support"></a>拡張機能とエコシステムのサポート

Visual Studio Live Share の主な目標の 1 つは、お気に入りの快適さから、互いと共同作業する開発者を有効にして[**大幅にカスタマイズされた**](https://marketplace.visualstudio.com/)ツール。 これにより、アドホックの相互作用は、頻繁に発生することが親しみやすく、人間工学を視覚的に、残り時間中にかに関係なくどのような支援を受けるとします。 これを実現することが重要コラボレーション セッション内の参加要素がサポートするすべての拡張機能の使用を続行できること、[個人設定とワークフロー](#user-specific-extensions) (例: カラー アイコン/テーマ、キー バインド、エディター生産性のお勧めの場合)。

さらに、として共同作業セッションに参加する動作は、できるだけ、生産性の高い、ながらインスタント Visual Studio Live Share の目的が自動的に、ホストが共有プロジェクト固有のツールを利用するゲストを有効にします。 これにより、単にリンクをクリックして、任意のツールを起動して、余分な設定を行わなくても、共同作業を開始できます。 これを実現することが重要その拡張機能は、コアの電源を[編集、ビルド、デバッグ ワークフロー](#project-specific-extensions)、ホストからゲストに「リモート」透過的ですそのため、など、オートコンプリート定義へ移動、およびデバッグ"。"に作業だけです。

このドキュメントでは、現在の既知の膨大な拡張機能のエコシステムの状態と、前述の目標の「スコアカード」について説明します。 拡張機能をこの条件を満たしていないし、個人のワークフローに不可欠ですが、発生した場合、ください[お知らせください。](https://github.com/MicrosoftDocs/live-share/issues/new)

## <a name="user-specific-extensions"></a>ユーザー固有の拡張機能

ユーザー固有のカスタマイズをサポートする拡張機能**する必要があります**ホストの作業と**する必要があります**すべてのゲストに対して動作します。 なります、回帰を Visual Studio Live Share のバグの可能性が場合は、拡張機能は、ホストの正常に動作しない、(ください[問題を報告](https://github.com/MicrosoftDocs/live-share/issues/new)いずれかが表示される場合。)。 かかる場合は、拡張機能は、ゲストの期待どおりに動作しない、[拡張機能自体の変更](#known-issues)、し、これらのシナリオのアドレス/改善するエコシステムと連携します。

### <a name="visual-studio-code"></a>Visual Studio Code

| Category | 例 | ゲストでサポートされているか。 | 共同作業しますか。 |
|-|-|-|-|
| 配色テーマ | [1 つの濃い Pro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme)、 [Colorizer を出力](https://marketplace.visualstudio.com/items?itemName=IBM.output-colorizer)、[虹文字列](https://marketplace.visualstudio.com/items?itemName=wk-j.vscode-rainbow-string)、[領域の色](https://github.com/jmihelcic/colored-regions)、[ブロックを強調表示のインデント](https://marketplace.visualstudio.com/items?itemName=byi8220.indented-block-highlighting)、 [Todo の強調表示](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight)、[ペア Colorizer 右山かっこ](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) | ✅ | *該当なし* |
| アイコン セット | [vscode アイコン](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons)、 [Visual Studio のクラシック アイコン](https://marketplace.visualstudio.com/items?itemName=jez9999.vsclassic-icon-theme) | ✅ | *該当なし* |
| キー バインド | [Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)、 [IntelliJ IDEA Keybindings](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings)、 [Emacs フレンドリ キーマップ](https://marketplace.visualstudio.com/items?itemName=lfs.vscode-emacs-friendly) | ✅ | *該当なし* |
| スニペット | [Angular v5 スニペット](https://marketplace.visualstudio.com/items?itemName=johnpapa.Angular2)、 [HTML スニペット](https://marketplace.visualstudio.com/items?itemName=abusaidm.html-snippets)、 [SVG アイコン](https://marketplace.visualstudio.com/items?itemName=idleberg.svg-icons)、[ファイル ヘッダー](https://marketplace.visualstudio.com/items?itemName=mikey.vscode-fileheader) | ✅ | *該当なし* <sup>1</sup> |
| 組織 | [設定の同期](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync)、[プロジェクト マネージャー](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager)、 [Timeit](https://marketplace.visualstudio.com/items?itemName=smulyono.timeit)、[チェックポイント](https://marketplace.visualstudio.com/items?itemName=micnil.vscode-checkpoints)、 [TODO パーサー](https://marketplace.visualstudio.com/items?itemName=minhthai.vscode-todo-parser)、[お気に入り](https://marketplace.visualstudio.com/items?itemName=kdcro101.favorites) (❌)[ブックマーク](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks)(❌) | ✅ <sup>2</sup> | *該当なし* <sup>3</sup> |
| 生産性 | [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)、[を自動的に変更タグ](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)、[コードのアウトライン](https://github.com/patrys/vscode-code-outline)、[強調表示色](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)、[選択範囲をインクリメント](https://marketplace.visualstudio.com/items?itemName=albymor.increment-selection)、 [Bracketeer](https://marketplace.visualstudio.com/items?itemName=pustelto.bracketeer)、[イメージのプレビュー](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-gutter-preview)、 [JSON ヘルパー](https://marketplace.visualstudio.com/items?itemName=zhoufeng.json-helper) (ポイント)[カラー ピッカー](https://marketplace.visualstudio.com/items?itemName=anseki.vscode-color)、[カーソル内の単語をコピー](https://marketplace.visualstudio.com/items?itemName=alefragnani.copy-word)、[CodeMetrics](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics) (CodeLens) [Git 共同作成者](https://github.com/rjimenezda/vscode-coauthor)、 [JavaScript ブースター](https://marketplace.visualstudio.com/items?itemName=sburg.vscode-javascript-booster) (CodeActions) [Turbo コンソール ログ](https://marketplace.visualstudio.com/items?itemName=ChakrounAnas.turbo-console-log)、 [Goto 次/前のメンバー](https://marketplace.visualstudio.com/items?itemName=mishkinf.goto-next-previous-member)、[自動スクロール](https://github.com/PejmanNik/vscode-autoScroll?files=1)、 [NPM インポート バージョン](https://marketplace.visualstudio.com/items?itemName=axetroy.vscode-npm-import-package-version)(❌)[コストをインポート](https://github.com/wix/import-cost)(❌) | ✅ <sup>2</sup> | ❌ <sup>3</sup> |
| Repl | [REST クライアント](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)、[コード ランナー](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)、 [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode)、 [R](https://marketplace.visualstudio.com/items?itemName=Ikuyadeu.r) | ✅ <sup>4</sup> | ❌ <sup>3</sup>  |
| リソース マネージャー | [mssql](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql)、 [ftp 単純](https://marketplace.visualstudio.com/items?itemName=humy2833.ftp-simple)、 [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions)、 [Docker](https://marketplace.visualstudio.com/items?itemName=PeterJausovec.vscode-docker)、 [Brew サービス](https://marketplace.visualstudio.com/items?itemName=beauallison.brew-services) | ✅ <sup>5</sup> | ❌ <sup>3</sup>  |

<sup>1</sup> *ユーザーは、スニペットを使い慣れてが既にして、使用できるとは、そのため、共有にすること必ずしも意味をなさないしない限り、します。*

<sup>2</sup> *これらの拡張機能のカテゴリは多岐にわたるなど、その操作と答えることはできません。ただし、理論上は、キーのないものを追跡します。*

<sup>3</sup> *コラボレーション エクスペリエンスは、これらの拡張機能のカテゴリが挙げられます、のでエンドユーザーからのフィードバックを把握する必要があります。*

<sup>4</sup> *ゲストにインストールされているランタイム ツール (例: Node.js) があり、コードをローカルで実行して作業する必要があります。*

<sup>5</sup> *何らかのサーバーに接続することでこれらと一元的なサーバーのいずれか、ゲストが共有するサーバーで動作できます。*

### <a name="visual-studio"></a>Visual Studio

もうすぐです。

## <a name="project-specific-extensions"></a>プロジェクト固有の拡張機能

編集、ビルド、デバッグ、アプリケーションの中核をサポートし、言語やプラットフォーム/ライブラリ/SDK に固有では、ホストにインストールされた拡張は、何もインストールする必要がないゲストを自動的に利用できるようにします。 これにより、ホスト、プロジェクトの生産性の高い開発をサポートするために、環境をセットアップでき客にすぐに、追加の前提条件なしに参加を許可します。 プロジェクト固有の拡張機能で把握する主観的または任意の方法で個人はないため、確定的に共有できるホストからゲストからの使い慣れた環境に影響を与えずにします。

さらに、ゲストがインストールされているプロジェクト固有の拡張機能が、ホストをサポートするためには、(1 つのファイルの intellisense を取得する、ドキュメントをフォーマットすること) 低下、まだ機能的なエクスペリエンスを提供するだけが理想的です。

| Category | 例 | 共有でしょうか。 | ゲストでサポートされているか。 |
|-------|----------|--------|-----|
| 文法と構文の強調表示 | [シェルの魚](https://marketplace.visualstudio.com/items?itemName=TeddyDD.fish)、 [Nginx](https://marketplace.visualstudio.com/items?itemName=shanoor.vscode-nginx)、 [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)、 [DotEnv](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv)、 [ES6 文字列 HTML](https://marketplace.visualstudio.com/items?itemName=hjb2012.vscode-es6-string-html)、 [Todo +](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-todo-plus)、[虹 CSV](https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv) | ❌ | ✅ |
| 言語サービス | [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)、[パス Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)、 [ARM](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools) | ✅ <sup>1</sup>| ✅ <sup>2</sup> |
| JSON スキーマ | [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions) | ✅ | ✅ |
| リンター | [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)、 [Markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)、[スペル チェックをコード](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)、 [PHPCS](https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs) | ✅ | ✅ <sup>2</sup>  |
| フォーマッタ | [わかりやすい](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)、[美化します。](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify) | ✅ | ✅ <sup>2</sup> |
| デバッガー | [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)、 [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) | ✅ <sup>3</sup> | ❌ <sup>4</sup> |
| テスト ランナー | [Java テスト ランナー](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-test)、 [Mocha サイドバー](https://marketplace.visualstudio.com/items?itemName=maty.vscode-mocha-sidebar)、 [Postman ランナー](https://marketplace.visualstudio.com/items?itemName=eridem.vscode-postman)、[冗談はランナー](https://marketplace.visualstudio.com/items?itemName=firsttris.vscode-jest-runner)、 [Neptune](https://marketplace.visualstudio.com/items?itemName=LambdaFactory.neptune) | ❌ <sup>5</sup> | ✅ <sup>2</sup> |
| カスタム ファイル プレビューアー | [SVG プレビュー](https://marketplace.visualstudio.com/items?itemName=cssho.vscode-svgviewer)、 [GraphViz](https://marketplace.visualstudio.com/items?itemName=joaompinto.vscode-graphviz)、 [Markdown イメージのサイズ](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-image-size) | ❌ |  ✅ |
| ファイルまたはプロジェクト ジェネレーター | [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions)、 [C と C++ プロジェクト ジェネレーター](https://marketplace.visualstudio.com/items?itemName=danielpinto8zz6.c-cpp-project-generator) | ❌ | ❌<sup>6</sup> |
| ソース管理プロバイダー | [SVN](https://marketplace.visualstudio.com/items?itemName=johnstoncode.svn-scm), [Hg](https://marketplace.visualstudio.com/items?itemName=mrcrowl.hg) | ❌ | ❌ |

<sup>1</sup> *現在のみC#および JavaScript または TypeScript で、その他のサポートが近日公開予定。*

<sup>2</sup> *ゲストはローカル ファイルへのアクセスがあるないため、現在のアクティブなドキュメントのみサポートします。*

<sup>3</sup> *中核的なデバッグ エクスペリエンスを共有、ただし、起動されたサーバーの転送は自動的にします。*

<sup>4</sup> *ゲストは、アプリのローカル コピーがないし、実行中のアプリと、デバッグ セッションがそのため、ホストのコンピューターで開始する必要があります。*

<sup>5</sup> *テストの実行の出力の結果として得られる端末、出力ウィンドウおよびエラーがゲストで共有されてもことが必要になります。*

<sup>6</sup> *、Node.js を使用して、これらのほとんどすべて`fs`、うまくいきません。 ファイルを作成するには、直接モジュール。*

### <a name="visual-studio"></a>Visual Studio

もうすぐです。

## <a name="known-issues"></a>既知の問題

次に、ゲスト (とその回避策)、共同作業セッションのコンテキスト内での動作を回避する可能性がありますし、そのため、ワークフローにも影響を与える現在認識されている拡張機能の問題を示します。

### <a name="visual-studio-code"></a>Visual Studio Code

| 懸案事項 | 理由 | 回避策 |
|-|-|-|
| Node.js を使用して`fs`モジュール ファイル (構成ファイルなど) の検出/読み取りまたはディレクトリの列挙 (および言語サービスがない)。 | ゲストには、ローカル ファイルへのアクセスを必要はありません。 | 1.ユーザー エクスペリエンスが適切に低下する *(可能な場合)。*<br /><br />2.使用して、`openTextDocument`と`findFiles`ワークスペース Api を読み取って、ファイルを列挙します。 |
| Node.js を使用して`fs`モジュールの作成またはファイルの書き込み | *上記と同じ* | *該当なし*を使用することができます、 `openTextDocument(Uri)` API を作成する、`untitled`ファイルを保存できませんが、特定のパスでファイル システムに直接します。 |
| プロジェクトにバンドルされているライブラリまたはツールに応じて | *上記と同じ* | 1.バンドルのフォールバックのバージョンの拡張機能と依存関係<br><br> 2.明示的にインストールする場合のゲストのブロックを解除するグローバルのインストールをサポートします。<br><br> 3.リモート ホストが必要で、右側の依存関係がありますので可能な場合の状態/アクションです。 |
| Node.js を使用して`fs`モジュール ディレクトリを作成するには | *上記と同じ* | *該当なし* |
| ドキュメントの機能を制限することでその使用、`file`スキーム。 | ゲストの側の使用上のファイル、`vsls`スキーム。 | サポートを追加`vsls`ドキュメント ([例](https://github.com/CoenraadS/BracketPair/pull/73)) |
| 使用して、`Uri.file`メソッドや`Uri.fsPath` / `TextDocument.fileName` Uri のシリアル化/解析するメンバー | *上記と同じ* | 使用`Uri.parse`と`Url.toString()`維持し、ファイル スキームを尊重する代わりに、([例](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| 使用して、`workspace.openTextDocument`メソッドの代わりにファイル パス、 `Uri` | *上記と同じ* | 提供、 `Uri` raw ファイルのパス文字列ではなくインスタンス ([例](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| 使用して、`workspace.rootPath`プロパティは、ワークスペースの存在を検出するには | `workspace.rootPath`プロパティ呼び出し`Uri.fsPath`を最初に`workspaceFolder`で、 `workspace`、上記で説明した同じ問題が発生します。 | 使用して、`workspace.workspaceFolders`プロパティを代わりに、ワークスペースの存在を検出し、必要な場合は、それぞれについて見て`workspaceFolder`の`Uri.scheme`それがローカルかどうかを判断するには |
| 言語サービスを登録するときに、ドキュメント スキーマを指定しない (いずれかによって、 `LanguageClient`、または`languages.register*`メソッド) | ゲストは、ローカルの拡張機能と、ホストの両方から言語サービスの結果を受信し、そのため、両方の参加者が同じ言語サービス拡張がインストールされている場合、ゲストが表示されます (オート コンプリート、コードの特定の情報の重複するエントリアクション) | 言語サービスを制限するだけで`file`と`untitled`スキーム ([例](https://github.com/vuejs/vetur/pull/756/files)) |
| ドキュメントをオンにしない`Uri.scheme`設定する前に、`DiagnosticCollection`その | *上記と同じ* | 生成のみ`Diagnostics`の`documents`が`Uri.scheme`  ===  `file` ([例](https://github.com/Huachao/vscode-restclient/pull/196)) |
| 返すときに、ワークスペースのスキームを確認していません`Tasks`カスタムから `TaskProvider`  | ゲスト、リモートとローカルですべてのタスクが表示されと表示重複両方の参加者がインストールされている同じ拡張機能がある場合  | のみを返す`Tasks`の`WorkspaceFolder`s が`Uri.scheme`  ===  `file` ([例](https://github.com/Microsoft/vscode-eslint/blob/0fdb7c74b093cae9dc08355e7235582a254f24c2/client/src/tasks.ts#L42)) |

### <a name="visual-studio"></a>Visual Studio

もうすぐです。

<!--

## Extensibility API

In addition to the core goals outlined in the beginning of this document, Live Share also wants to enable extension authors to enhance the default sharing experience in the following ways:

1. Contributing to the core collaborative feature set, based on behavior that only the extension would know about. In these scenarios, the host could have an extension installed, and potentially allow guests to benefit from it without also needing to have it installed

2. Enhancing their own experiences to be collaborative (e.g. syncing bookmarks between participants), by synchronizing any custom state and UI interactions. In these scenarios, only participants that had the custom extension installed would be able to take advantage of the added collaboratively.

This will require some form of API/SDK, which extensions can use to determine if/when the end-user is within a Live Share session, and if so, light up additional capabilities. The following represents a high-level overview of some of the extension points we've identified, and look forward to getting further feedback on:

| Shared Resource | Extensibility Point(s) |
|------------------|---------------------|
| User status | 1. Retrieving the list of participants within the current Live Share session (e.g. the [Git Co-Authors](https://marketplace.visualstudio.com/items?itemName=drrouman.git-coauthors) extension could use that to populate the host's commit message with)<br /><br /> 2. Updating a participant's location (outside of just editors), as well as allowing other participant's to jump to/pin to them as they move into custom extension UI (e.g. a participant is navigating a MongoDB database using the [Azure Cosmos DB](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb) extension). |
| Workspace | *N/A* - Live Share can transparently share all files, edits, cursors and highlights, without requiring an extension to do anything extra if it modified the file system and/or cursor/highlight position. |
| Language Services | *N/A* - Long-term, Live Share can transparently remote all language services (e.g. go to definition, document formatting, CodeLens) to the guest, including those that are contributed via extensions (e.g. [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)) |
| Debugging Sessions | *N/A* - Live Share can transparently remote all debugging sessions, including those that are enabled by custom extensions (e.g. [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)) |
| Servers | 1. Sharing a server that an extension was responsible for starting, and then optionally specifying whether a browser should be launched on the guest's machine as well (e.g. a debug adapter that launched a web server).  |
| Custom | 1. Synchronizing arbitrary state and/or user interactions (e.g. the [Bookmarks](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) extension syncing CRUD operations across participants, the [Maven for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-maven) extension exposing the project-wide view to guests) |

-->

## <a name="see-also"></a>関連項目

- [言語とプラットフォームのサポート](platform-support.md)
- [Live Share の接続要件](connectivity.md)
- [Live Share のセキュリティ機能](security.md)
- [すべての主要なバグ、機能要求、および制限事項](https://aka.ms/vsls-issues)
- [すべての機能要求や制限事項](https://aka.ms/vsls-feature-requests)

問題が発生していますか? [トラブルシューティング](../troubleshooting.md)または[フィードバックの送信](../support.md)に関するページをご覧ください。
