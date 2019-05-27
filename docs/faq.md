---
title: FAQ - Visual Studio の Live Share |Microsoft Docs
description: Visual Studio Live Share に関するよく寄せられる質問。
ms.custom: ''
ms.date: 05/05/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 91ffc42c06e70839dbadbd2487cd02970ded3346
ms.sourcegitcommit: bfa1020882095fcc7d31cd71cf1f2e601e3bea06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2019
ms.locfileid: "66224710"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="frequently-asked-questions"></a>よく寄せられる質問

## <a name="what-is-live-share"></a>Live Share とは何ですか。
Live Share を使うと、使っているプログラミング言語や構築しているアプリの種類に関係なく、リアルタイムで他のユーザーと共同で編集したりデバッグしたりできます。 瞬時に (かつ安全に)、現在のプロジェクトを共有し、必要に応じて、デバッグ セッション、ターミナルのインスタンス、localhost の web アプリ、およびを共有することができます。 ユーザーは、セッションに参加する開発者を実行できる任意のリポジトリを複製するか、任意の Sdk をインストールすることがなく、すぐに生産的共同作業を開始できるように、環境 (例: 言語サービスのデバッグ) から、エディターのコンテキストのすべてを受信します。

## <a name="what-are-the-tooling-requirements-for-using-live-share"></a>Live Share を使用するためのツールの要件とは
[コア機能](#what-are-the-core-capabilities-of-live-share)Live Share は完全にサポートで、次のツール。

* [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
* [Visual Studio 2017 (15.6 以降)](https://visualstudio.microsoft.com/vs/older-downloads/)
* [Visual Studio Code](https://code.visualstudio.com/)

処理してすばやくユーザーからのフィードバックに応答します。 Visual Studio 内の機能を活用する必要があり、のみである Visual Studio Code は、そのそれぞれプレビュー/insider のリリースで利用できます。 機能に必要な VS または VS Code のドキュメントの最新バージョンが示されます。 たとえば、ローカルの元に戻す/やり直しのサポートには、Visual Studio 2017 15.7 + が必要です。

## <a name="what-are-the-core-capabilities-of-live-share"></a>Live Share のコア機能とは
ライブの共有では、共有することができます、コードベースをセキュリティで保護された接続経由でチーム メンバーとします。 ライブの共有を使用した共同ワークスペース内の複数のファイルを編集することができると、重要なは、チーム メンバーを使用してアプリケーションをデバッグの詳細は。 共同編集内容を編集中にすぐに表示することは他のチーム メンバー。 併置デバッグ中に、アプリケーションの同じデバッグ セッションを共有しています。 つまりと他のチーム メンバーは、ブレークポイントやステップ実行を使用したプログラム実行を制御できますが、個別に検査できましていない変数、ウォッチ、ローカル、Repl (例: Visual Studio のイミディ エイト ウィンドウ)。

ライブの共有などさまざまなユース ケースがありますバグの調査を同時に、他のユーザーのコンピューターには、再現コードはありませんが、問題を引き起こしているデザインを解決する問題には、ペア プログラミング、実施、インタビューをコーディング、メンタリング、チームの他のメンバーまたはを実行する。アドホック コードを確認します。

## <a name="by-using-live-share-is-my-code-stored-on-a-microsoft-server"></a>Live Share を使用すると、Microsoft のサーバーに格納されているコードですか。
いいえ、共有コードは、共有を開始した開発者のマシンにのみ存在します。 または格納されない任意の方法でクラウドにアップロードします。 代わりに、Live Share だけです (つまり暗号化されたエンド ツー エンド) する同僚との間のセキュリティで保護された接続を確立ししない検査または共有されるコードの任意のデータを収集します。

## <a name="does-this-remote-based-model-work-anywhere-is-it-peer-to-peer"></a>このリモート ベースのモデルは作業どこですか。 ピア ツー ピアですか。
ライブの共有の唯一の要件は、共有相手のユーザーとその味方がゴールにインターネットへのアクセスがあることです。 コラボレーション セッション中にチーム メンバー間のセキュリティで保護された通信は、Azure relay によって促進されます。 ワークスペース (ソース ファイル) は、クラウドでは保存されません。 特殊なピア ツー ピア接続は必要ありませんが、1 つは、待機時間を短縮に使用する場合があります。 参照してください[接続モードを変更する](https://aka.ms/vsls-docs/connection-mode)詳細については、ドキュメントにします。

## <a name="what-is-shared-during-a-live-share-session"></a>Live Share セッション中に共有しますか。
ライブの共有は、すべてのキーボードとマウス入力を転送しません。 また、チーム メンバーのマシンに共同作業アクティビティごとに必要なデータのみ通信します。 たとえば、ワークスペースを共有すると、フォルダー構造が共有されます。 共同でファイルを編集する場合は、そのファイルの内容が共有されます。 共同でデバッグしている場合は、(ステップ実行など) のデバッグ操作と状態 (例: 呼び出し履歴およびローカル変数) が共有されます。

## <a name="when-will-live-share-be-released"></a>Live Share をいつリリースされますか。
ライブの共有が一般公開です。 できます[Live Share 概要](https://aka.ms/vsls-start)今日です。

## <a name="how-much-will-it-cost"></a>いくらですか。
Visual Studio Live Share 継続的に使用する開発者向けの実質的な free レベルに取り組んでいます。 私たちを評価して高度な機能の有料レベルの導入ように、コミュニティのニーズを理解しました。

## <a name="how-is-my-code-shared-with-other-teammates"></a>その他の共同のマイ コードの共有方法
Live Share を使用する場合は、チームメイトからアクセスできる、セキュリティで保護されたクラウド サービス経由でリモート コマンド エディターとして使用するように使用できる作業中のコードを加えていません。 他のチーム メンバーが開き、またはクラウドに保存して、完全にチームメイトがコンピューターに保存することがなく、ファイルを編集できます。

ライブの共有では、プロジェクト ツリー、コード ナビゲーション、検索のような機能にすぐにアクセスできるようにします。 また、チームメイト エディターの IntelliSense などの機能強化からメリットを得ることもできます。

## <a name="what-happens-if-a-user-goes-offline-or-stops-sharing"></a>内容は、ユーザーがオフラインになったまたは共有を停止した場合どうなりますか。
リモートのモデルでは、オンライン接続している Live Share し、その味方がゴールを使用した共有開発者である必要がありますが必要です。 チームメイトは、オフラインのときに Live Share を使用すると、これらが再びオンラインになるまでのセッションに参加することできませんは。 さらに、コラボレーション停止します (例: してエディターを閉じます、オフライン、または停止する共有)、アクションまたは他のチーム メンバーによるファイル アクセスをさらに、後はすぐに無効になります。

## <a name="what-about-screen-sharing"></a>画面共有何ですか。
ライブの共有を使用して、プロジェクトのコードとそのコンテキストを共有できます。 チームメイトのコードベースへのジャンプはあり、使い慣れたツールを使用して、お客様と協力できます簡単になります。 エディターまたは他のアプリケーションが共有または表示可能なチームメイトとなワーク スタイルを変更または web ベースのアプリを使用する必要はありません。

ライブの共有では、画面共有メニュー項目を表示したり、アプリまたはエディターの視覚的な側面について説明することがありますは置き換えられません。 代わりに、チャット、音声、ビデオ、および画面共有と共に Live Share を使用するオプションがあります。

## <a name="what-about-other-collaboration-tools"></a>その他のコラボレーション ツールについて説明します。
ライブの共有は、チャット、インスタント メッセージング、または電子メールのテクノロジを使用できます。 これらのツールで開発者の間の多くの共同対話を開始することを観察しましたしました。 ただし、コードに関する説明がある場合、多くの場合を利用が単にすぎるテキストやコード スニペットでは、1 つのファイルの問題を説明する詳細なコンテキストが必要です。

ライブの共有をなど、多くのことを使用できます: ペア プログラミング、コーディングのインタビューを実施する、または、アドホック実行するは、バグを解決する問題のヘルプを求めているコードのコミットまたはプル要求の前に確認してください。

## <a name="what-about-other-web-editors"></a>その他の web エディターについて説明します。
Web ベースのエディターでは、両方のチーム メンバーは同じ web アプリを使用して、プライマリの日常的なエディターができない可能性があります、コラボレーションのメリットを取得する必要があります。 多くの web ベースのエディターでは、構築とクラウド環境で多くの場合、ホストされている仮想マシンへのデプロイが前提としています。

これは、多くのシナリオに適した、開発者は多くの場合は、VM またはクラウドにホストされているアプリでの共同作業します。  Live Share を使用して、チームメイトが web ベースのエディターで利用できる同じ機能に加えて、このツールのエコシステムの機能を使用できます。

ライブの共有を使用して、ステップをさらには、デバッグ セッションを共有することができます。  これにより、開発ワークフローを変更することや、アプリケーションの設計を変更することなしにコンピューターにのみ発生する問題を追跡するための他のユーザーへの参加に特に便利です。

## <a name="which-languages-and-platforms-will-be-supported"></a>どの言語とプラットフォームがサポートされますか。
目標は、多様な言語とプラットフォーム、開発中、アプリケーションの種類に関係なく、機能豊富なコラボレーションを有効にできることを確認する規制をサポートするためにです。 参照してください、[言語とプラットフォームのサポート](reference/platform-support.md)に関する記事の詳細について今すぐ動作をします。

## <a name="how-many-developers-can-join-a-collaboration-session"></a>開発者の数は、コラボレーション セッションに参加できますか。
現在サポートされています (「ホスト」) を共有している開発者だけでなく、30 の同時実行のゲストのプロジェクト。 

## <a name="what-is-the-roadmap"></a>ロードマップとは何ですか。
既知の問題、およびロードマップ項目のセットを表示する[ここ](https://aka.ms/vsls-issues)します。 すべての問題ではなく、機能の要求のみを参照する場合を参照してください。[ここ](https://aka.ms/vsls-feature-requests)します。 勧めを既存の項目を投票、ファイルの新しい機能の要求、およびバグの報告、協力するためにログに記録する図形、製品の今後の方向。

## <a name="see-also"></a>関連項目

- [言語とプラットフォームのサポート](platform-support.md)
- [Live Share の接続要件](reference/connectivity.md)
- [Live Share のセキュリティ機能](reference/security.md)
- [すべての主要なバグ、機能要求、および制限事項](https://aka.ms/vsls-issues)
- [すべての機能要求および制限事項](https://aka.ms/vsls-feature-requests)

問題が発生していますか? [トラブルシューティング](troubleshooting.md)または[フィードバックの送信](support.md)に関するページをご覧ください。
