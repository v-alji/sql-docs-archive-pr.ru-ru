---
title: MSSQLSERVER_9524 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9524 (Database Engine error)
ms.assetid: 12da7931-e124-4466-889c-046f1b7b7bfd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6c46ee0ef0bd1be299614e2cb04a3d6cd99d92e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658751"
---
# <a name="mssqlserver_9524"></a><span data-ttu-id="06bc7-102">MSSQLSERVER_9524</span><span class="sxs-lookup"><span data-stu-id="06bc7-102">MSSQLSERVER_9524</span></span>
    
## <a name="details"></a><span data-ttu-id="06bc7-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="06bc7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="06bc7-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="06bc7-104">Product Name</span></span>|<span data-ttu-id="06bc7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="06bc7-105">SQL Server</span></span>|  
|<span data-ttu-id="06bc7-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="06bc7-106">Event ID</span></span>|<span data-ttu-id="06bc7-107">9254</span><span class="sxs-lookup"><span data-stu-id="06bc7-107">9254</span></span>|  
|<span data-ttu-id="06bc7-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="06bc7-108">Event Source</span></span>|<span data-ttu-id="06bc7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="06bc7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="06bc7-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="06bc7-110">Component</span></span>|<span data-ttu-id="06bc7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="06bc7-111">SQLEngine</span></span>|  
|<span data-ttu-id="06bc7-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="06bc7-112">Symbolic Name</span></span>|<span data-ttu-id="06bc7-113">XMLERR_INVALID_COLUMNSET_XML</span><span class="sxs-lookup"><span data-stu-id="06bc7-113">XMLERR_INVALID_COLUMNSET_XML</span></span>|  
|<span data-ttu-id="06bc7-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="06bc7-114">Message Text</span></span>|<span data-ttu-id="06bc7-115">Переданное XML-содержимое не соответствует установленному формату XML для наборов разреженных столбцов.</span><span class="sxs-lookup"><span data-stu-id="06bc7-115">The XML content provided does not conform to the required XML format for sparse column sets.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="06bc7-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="06bc7-116">Explanation</span></span>  
 <span data-ttu-id="06bc7-117">Была предпринята попытка изменить набор столбцов.</span><span class="sxs-lookup"><span data-stu-id="06bc7-117">An attempt was made to modify a column set.</span></span> <span data-ttu-id="06bc7-118">XML-содержимое набора столбцов должно соответствовать ограничениям формата для набора столбцов.</span><span class="sxs-lookup"><span data-stu-id="06bc7-118">The XML content of a column set must meet the format restrictions of a column set.</span></span> <span data-ttu-id="06bc7-119">Стандартный формат набора столбцов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="06bc7-119">The general format of a column set is as follows:</span></span>  
  
 `<column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...`  
  
 <span data-ttu-id="06bc7-120">Дополнительные сведения о наборах столбцов см. в разделе «Использование наборов столбцов» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06bc7-120">For more information about column sets, see the topic "Using Column Sets" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="06bc7-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="06bc7-121">User Action</span></span>  
 <span data-ttu-id="06bc7-122">Исправьте формат XML для набора столбцов в инструкции.</span><span class="sxs-lookup"><span data-stu-id="06bc7-122">Correct the format of the XML for the column set in the statement.</span></span>  
  
  
