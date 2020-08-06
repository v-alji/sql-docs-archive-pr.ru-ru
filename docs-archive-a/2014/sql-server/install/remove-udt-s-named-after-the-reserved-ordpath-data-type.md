---
title: Удалить определяемый пользователем тип&#39;s с именем, зарезервированным с помощью типа данных НЕВЕРНАЯ ORDPATH | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 474e910a-6abb-4e28-acc2-055338c011d4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0528d19de17781d863e3a42fdef7db558fe5d190
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751700"
---
# <a name="remove-udt39s-named-after-the-reserved-ordpath-data-type"></a><span data-ttu-id="882e4-102">Удалить определяемый пользователем тип&#39;s с именем после зарезервированного типа данных НЕВЕРНАЯ ORDPATH</span><span class="sxs-lookup"><span data-stu-id="882e4-102">Remove UDT&#39;s named after the reserved ORDPATH data type</span></span>
  <span data-ttu-id="882e4-103">Помощник по обновлению обнаружил определяемый пользователем тип, имя которого совпадает с именем, зарезервированным для типа данных `ORDPATH`.</span><span class="sxs-lookup"><span data-stu-id="882e4-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for the `ORDPATH` data type.</span></span>  
  
## <a name="component"></a><span data-ttu-id="882e4-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="882e4-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="882e4-105">Описание</span><span class="sxs-lookup"><span data-stu-id="882e4-105">Description</span></span>  
 <span data-ttu-id="882e4-106">Имена терминов, используемых во встроенных типах данных, не должны использоваться в качестве имен определяемых пользователем типов среды CLR или их псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="882e4-106">The terms used for built-in data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="882e4-107">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="882e4-107">Corrective Action</span></span>  
 <span data-ttu-id="882e4-108">Удалите определяемый пользователем тип и создайте его повторно с именем, отличным от зарезервированного.</span><span class="sxs-lookup"><span data-stu-id="882e4-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="882e4-109">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="882e4-109">External Resources</span></span>  
 [<span data-ttu-id="882e4-110">Создание определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="882e4-110">Creating a User-Defined Type</span></span>](../../relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types.md)  
  
  
