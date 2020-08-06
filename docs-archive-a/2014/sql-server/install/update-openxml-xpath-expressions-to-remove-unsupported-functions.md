---
title: Обновление выражений OPENXML XPath для удаления неподдерживаемых функций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- OPENXML queries
ms.assetid: b459abaf-8787-4b65-9231-ae30e5469fd0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2c64408d6d705654014b6d071012001374a5f486
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659142"
---
# <a name="update-openxml-xpath-expressions-to-remove-unsupported-functions"></a><span data-ttu-id="6da8c-102">Обновите выражения XPath OPENXML, удалив неподдерживаемые функции</span><span class="sxs-lookup"><span data-stu-id="6da8c-102">Update OPENXML XPath expressions to remove unsupported functions</span></span>
  <span data-ttu-id="6da8c-103">Помощник по обновлению обнаружил использование функциональности XPath.</span><span class="sxs-lookup"><span data-stu-id="6da8c-103">Upgrade Advisor detected the use of XPath functionality.</span></span> <span data-ttu-id="6da8c-104">Работу некоторых приложений могут затронуть изменения в функциональности XPath для компонентов OPENXML после обновления.</span><span class="sxs-lookup"><span data-stu-id="6da8c-104">You may be affected by changes in XPath functionality for OPENXML features after you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="6da8c-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="6da8c-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="6da8c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6da8c-106">Description</span></span>  
 <span data-ttu-id="6da8c-107">MSXML 3.0 является теперь базовым обработчиком выражений XPath, используемых в запросах OPENXML.</span><span class="sxs-lookup"><span data-stu-id="6da8c-107">MSXML 3.0 is now the underlying engine that is used to process XPath expressions that are used within OPENXML queries.</span></span> <span data-ttu-id="6da8c-108">MSXML 3.0 имеет ядро, более строго соответствующее спецификации XPath 1.0, где была отменена поддержка следующих функций:</span><span class="sxs-lookup"><span data-stu-id="6da8c-108">MSXML 3.0 has a stricter XPath 1.0 engine in which support for the following functions has been removed:</span></span>  
  
-   <span data-ttu-id="6da8c-109">format-number();</span><span class="sxs-lookup"><span data-stu-id="6da8c-109">format-number()</span></span>  
  
-   <span data-ttu-id="6da8c-110">formatNumber();</span><span class="sxs-lookup"><span data-stu-id="6da8c-110">formatNumber()</span></span>  
  
-   <span data-ttu-id="6da8c-111">current();</span><span class="sxs-lookup"><span data-stu-id="6da8c-111">current()</span></span>  
  
-   <span data-ttu-id="6da8c-112">element-available();</span><span class="sxs-lookup"><span data-stu-id="6da8c-112">element-available()</span></span>  
  
-   <span data-ttu-id="6da8c-113">function-available();</span><span class="sxs-lookup"><span data-stu-id="6da8c-113">function-available()</span></span>  
  
-   <span data-ttu-id="6da8c-114">system-property().</span><span class="sxs-lookup"><span data-stu-id="6da8c-114">system-property()</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="6da8c-115">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="6da8c-115">Corrective Action</span></span>  
 <span data-ttu-id="6da8c-116">Вместо функций format-number() и formatNumber() можно использовать [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6da8c-116">In the case of format-number() and formatNumber(), you can use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6da8c-117">Для других неподдерживаемых функций, перечисленных ранее, прямой альтернативы нет.</span><span class="sxs-lookup"><span data-stu-id="6da8c-117">For the other unsupported functions listed earlier, there is no direct workaround.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6da8c-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="6da8c-118">See Also</span></span>  
 <span data-ttu-id="6da8c-119">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="6da8c-119">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="6da8c-120">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="6da8c-120">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
