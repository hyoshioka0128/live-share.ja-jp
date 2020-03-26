---
title: ユーザープロファイル-Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live Share ユーザープロファイルを表示および削除する方法の概要について説明します。
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
ms.openlocfilehash: 2f9f496b47db7efe260c1f09a2906c68c07762d5
ms.sourcegitcommit: 6bf13781dc42a2bf51a19312ede37dff98ab33ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "80295931"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>ユーザー プロファイル

Visual Studio Live Share で認証すると、ユーザープロファイルが作成されます。これにより、共同作業を行った参加者 (たとえば、電子メールアドレス、アバター) を確認することができます。 任意の時点で、次のいずれかのページに移動して (使用した id プロバイダーに応じて)、Live Share に格納されているプロファイル情報を表示できます。

- [Microsoft アカウント/Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

このページでは、(本人確認のために) サインインするようにというメッセージが表示され、ユーザープロファイルの未加工の JSON 出力が表示されます。

<img width="500px" src="media/user-profile.png" />

ログインに使用した id に対してプロファイルが保存されていない場合は、そのことも通知されます。 Visual Studio Live Share。

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>プロファイルを削除しています

ユーザープロファイルを削除する場合は、[[ユーザープロファイル] ページ](#user-profile)の [`Delete your account`] ボタンをクリックします。 そうしないと、最後に成功したサインインから30日後にプロファイルが自動的に削除され Visual Studio Live Share ます。 このコンテキストでは、"成功したサインイン" とは、(使用しているツールに応じて) 次のことを意味します。

| IDE/エディター | ユーザープロファイルは、最後の30日後に削除されます... |
|-|-|
| Visual Studio | IDE の新しいインスタンスを起動します。 シングルサインオンをサポートするために、Visual Studio Live Share は、Visual Studio の新しいインスタンスを開くたびに認証セッションを更新します。 |
| Visual Studio Code | ブラウザーベースの認証ワークフローを完了します (たとえば、[`Sign In`] ボタンをクリックするか、`Live Share: Sign in with browser` コマンドを実行します)。 Visual Studio Live Share は、を共有するたびにサインインする必要がないように、クライアントで認証セッションを記憶します。 ただし、そのセッションは30日後に有効期限が切れ、ブラウザーを使用して明示的にサインインするまで、自動的に更新されることはありません。 |

## <a name="see-also"></a>参照

- [言語とプラットフォームのサポート](reference/platform-support.md)
- [Live Share の接続要件](reference/connectivity.md)
- [Live Share のセキュリティ機能](reference/security.md)
- [すべての主要なバグ、機能要求、および制限事項](https://aka.ms/vsls-issues)
- [すべての機能要求および制限事項](https://aka.ms/vsls-feature-requests)

問題が発生していますか? [トラブルシューティング](troubleshooting.md)または[フィードバックの送信](support.md)に関するページをご覧ください。
