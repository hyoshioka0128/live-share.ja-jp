---
title: ユーザー プロファイル - Visual Studio の Live Share |Microsoft Docs
description: 表示および Visual Studio Live Share ユーザー プロファイルを削除する方法の概要。
ms.custom: ''
ms.date: 05/222/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 38fb6fada1030bddac8f3437f19f0ae259f5626e
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640030"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>ユーザー プロファイル

Visual Studio Live Share を認証する場合、ユーザー プロファイルが作成、参加者がユーザーを表示すると共同作業できる (電子メール アドレス、アバターなど)。 任意の時点では、(id プロバイダーを使用した) に応じて、次のページのいずれかに移動して、お客様に代わって Live Share が格納されているプロファイル情報を表示できます。

- [Microsoft アカウントまたは Azure Active Directory](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

ページは、お客様の本人確認にサインインするように求めし、ユーザー プロファイルの未加工の JSON 出力を表示します。

<img width="500px" src="media/user-profile.png" />

Visual Studio Live Share 現在格納されているログインで使用する id のプロファイルはありません場合、確認することをもします。

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>プロファイルを削除します。

ユーザー プロファイルを削除する場合は、というリンクをクリックすることができます`Click here to get your data removed from our systems`上、[ユーザー プロファイル ページ](#user-profile)します。 直接 (id プロバイダーを使用した) に応じて、次のページのいずれかをアクセスすることができます。

- [Microsoft アカウントまたは Azure Active Directory](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/deleteme)
- [GitHub](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/github/deleteme)

それ以外の場合、Visual Studio Live Share は自動的に削除、プロファイルの 30 日後、最後に正常にサインインします。 このコンテキストで、「成功したサインイン」(使用しているツール) に応じて、次を参照します。

| IDE やエディター | ユーザー プロファイルには、最後後 30 日間を削除しています. |
|-|-|
| Visual Studio | IDE の新しいインスタンスを起動します。 シングル サインオンをサポートするためには、Visual Studio Live Share は、Visual Studio の新しいインスタンスを開くたびに、認証セッションを更新します。 |
| Visual Studio Code | ブラウザー ベースの認証ワークフローの完了 (例: クリックすると、`Sign In`ボタンまたはを実行している、`Live Share: Sign in with browser`コマンド)。 Visual Studio Live Share とサインインを共有するたびにする必要があるを防止するため、クライアントの認証セッションが記憶されます。 ただし、そのセッションでは、30 日後、有効期限が切れるしする明示的なブラウザーでもう一度サインインするまで自動的に更新します。 |

## <a name="see-also"></a>関連項目

- [言語とプラットフォームのサポート](reference/platform-support.md)
- [Live Share の接続要件](reference/connectivity.md)
- [Live Share のセキュリティ機能](reference/security.md)
- [すべての主要なバグ、機能要求、および制限事項](https://aka.ms/vsls-issues)
- [すべての機能要求および制限事項](https://aka.ms/vsls-feature-requests)

問題が発生していますか? [トラブルシューティング](troubleshooting.md)または[フィードバックの送信](support.md)に関するページをご覧ください。
