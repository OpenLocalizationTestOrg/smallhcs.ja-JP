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
# <a name="entities-and-activity-types"></a><span data-ttu-id="43c41-104">エンティティとアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="43c41-104">Entities and activity types</span></span>

<span data-ttu-id="43c41-105">エンティティはアクティビティの一部であり、アクティビティまたは会話に関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="43c41-105">Entities are a part of an activity, and provide additional information about the activity or conversation.</span></span>

[!include[Entity boilerplate](includes/C1-snippet-entity-boilerplate.md)]

## <a name="entities"></a><span data-ttu-id="43c41-106">会社</span><span class="sxs-lookup"><span data-stu-id="43c41-106">Entities</span></span>

<span data-ttu-id="43c41-107">メッセージの*エンティティ*プロパティは、チャネルとボットの間で共通のコンテキストメタデータを交換することを可能にする、オープンエンドの<a href="http://schema.org/" target="_blank">schema.org</a>オブジェクトの配列です。</span><span class="sxs-lookup"><span data-stu-id="43c41-107">The *entities* property of a message is an array of open-ended <a href="http://schema.org/" target="_blank">schema.org</a> objects which allows the exchange of common contextual metadata between the channel and bot.</span></span>

### <a name="mention-entities"></a><span data-ttu-id="43c41-108">エンティティのメンション</span><span class="sxs-lookup"><span data-stu-id="43c41-108">Mention entities</span></span> 

<span data-ttu-id="43c41-109">多くのチャネルでは、ユーザーが会話のコンテキスト内で他のユーザーを "メンション" する機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="43c41-109">Many channels support the ability for a bot or user to "mention" someone within the context of a conversation.</span></span>
<span data-ttu-id="43c41-110">メッセージでユーザーにメンションするには、メッセージの [エンティティ] プロパティに*メンション*するオブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="43c41-110">To mention a user in a message, populate the message's entities property with a *mention* object.</span></span>
<span data-ttu-id="43c41-111">メンションオブジェクトには、次のプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="43c41-111">The mention object contains these properties:</span></span>

| <span data-ttu-id="43c41-112">プロパティー</span><span class="sxs-lookup"><span data-stu-id="43c41-112">Property</span></span> | <span data-ttu-id="43c41-113">説明</span><span class="sxs-lookup"><span data-stu-id="43c41-113">Description</span></span> |
|----|----|
| <span data-ttu-id="43c41-114">種類</span><span class="sxs-lookup"><span data-stu-id="43c41-114">Type</span></span> | <span data-ttu-id="43c41-115">エンティティの種類 ("メンション")</span><span class="sxs-lookup"><span data-stu-id="43c41-115">type of the entity ("mention")</span></span> |
| <span data-ttu-id="43c41-116">メンション</span><span class="sxs-lookup"><span data-stu-id="43c41-116">Mentioned</span></span> | <span data-ttu-id="43c41-117">どのユーザーがメンションされたかを示すチャネルアカウントオブジェクト</span><span class="sxs-lookup"><span data-stu-id="43c41-117">channel account object that indicates which user was mentioned</span></span> | 
| <span data-ttu-id="43c41-118">テキスト</span><span class="sxs-lookup"><span data-stu-id="43c41-118">Text</span></span> | <span data-ttu-id="43c41-119">メンション自体を表す text プロパティ (空または null の場合もあります) のテキスト *。*</span><span class="sxs-lookup"><span data-stu-id="43c41-119">text within the *activity.text* property that represents the mention itself (may be empty or null)</span></span> |

<span data-ttu-id="43c41-120">次のコード例は、メンションエンティティを entity コレクションに追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="43c41-120">This code example shows how to add a mention entity to the entities collection.</span></span>

# <a name="ctabcs"></a>[<span data-ttu-id="43c41-121">C-clip#</span><span class="sxs-lookup"><span data-stu-id="43c41-121">C#</span></span>](#tab/cs)
[!code-csharp[set Mention](includes/code/C1-dotnet-create-messages.cs#setMention)]

