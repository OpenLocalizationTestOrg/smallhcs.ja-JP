---
title: エンティティとアクティビティの種類 |Microsoft ドキュメント
description: エンティティとアクティビティの種類。
keywords: エンティティのメンション、アクティビティの種類、使用するエンティティ
author: ivorb
ms.author: v-ivorb
manager: kamrani
ms.topic: article
ms.service: bot-service
ms.subservice: sdk
ms.date: 03/01/2018
ms.openlocfilehash: d4f8eb7c66c90dc7df7c09738d931b44057ef593
ms.sourcegitcommit: b7432e53415fba697a23cad2d7e2dc4e0d2b89c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "6606626"
---
# <a name="entities-and-activity-types"></a>エンティティとアクティビティの種類

エンティティはアクティビティの一部であり、アクティビティまたは会話に関する追加情報を提供します。

[!include[Entity boilerplate](includes/C1-snippet-entity-boilerplate.md)]

## <a name="entities"></a>会社

メッセージの*エンティティ*プロパティは、チャネルとボットの間で共通のコンテキストメタデータを交換することを可能にする、オープンエンドの<a href="http://schema.org/" target="_blank">schema.org</a>オブジェクトの配列です。

### <a name="mention-entities"></a>エンティティのメンション 

多くのチャネルでは、ユーザーが会話のコンテキスト内で他のユーザーを "メンション" する機能をサポートしています。
メッセージでユーザーにメンションするには、メッセージの [エンティティ] プロパティに*メンション*するオブジェクトを設定します。
メンションオブジェクトには、次のプロパティが含まれます。

| プロパティー | 説明 |
|----|----|
| 種類 | エンティティの種類 ("メンション") |
| メンション | どのユーザーがメンションされたかを示すチャネルアカウントオブジェクト | 
| テキスト | メンション自体を表す text プロパティ (空または null の場合もあります) のテキスト *。* |

次のコード例は、メンションエンティティを entity コレクションに追加する方法を示しています。

# <a name="ctabcs"></a>[C-clip#](#tab/cs)
[!code-csharp[set Mention](includes/code/C1-dotnet-create-messages.cs#setMention)]

