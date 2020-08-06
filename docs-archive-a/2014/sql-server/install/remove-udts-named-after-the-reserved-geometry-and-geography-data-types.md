---
title: Удалите определяемые пользователем типы, названные после зарезервированных геометрических и географических типов данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- geometry data type [SQL Server], UDTs
- geography data type [SQL Server], UDTs
ms.assetid: a167ce3a-50b4-4e77-a884-adb23b586c72
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4977d45d53e1114edc8e04ad504963bae0b9eb9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751699"
---
# <a name="remove-udts-named-after-the-reserved-geometry-and-geography-data-types"></a><span data-ttu-id="d2cc0-102">Удалите определяемые пользователем типы с именами, совпадающими с зарезервированными типами данных GEOMETRY и GEOGRAPHY</span><span class="sxs-lookup"><span data-stu-id="d2cc0-102">Remove UDTs named after the reserved GEOMETRY and GEOGRAPHY data types</span></span>
  <span data-ttu-id="d2cc0-103">Помощник по обновлению обнаружил определяемый пользователем тип, имя которого совпадает с именем, зарезервированным для типа данных `geometry` или `geography`.</span><span class="sxs-lookup"><span data-stu-id="d2cc0-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for either the `geometry` or the `geography` data types.</span></span> <span data-ttu-id="d2cc0-104">Типы данных `geometry` и `geography` являются частью компонента для обработки пространственных данных.</span><span class="sxs-lookup"><span data-stu-id="d2cc0-104">The `geometry` and `geography` data types are part of the spatial data feature.</span></span>  
  
## <a name="component"></a><span data-ttu-id="d2cc0-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="d2cc0-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="d2cc0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d2cc0-106">Description</span></span>  
 <span data-ttu-id="d2cc0-107">Имена терминов, используемых в типах пространственных данных, не должны использоваться в качестве имен определяемых пользователем типов среды CLR или их псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="d2cc0-107">The terms used for spatial data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="d2cc0-108">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="d2cc0-108">Corrective Action</span></span>  
 <span data-ttu-id="d2cc0-109">Удалите определяемый пользователем тип и создайте его повторно с именем, отличным от зарезервированного.</span><span class="sxs-lookup"><span data-stu-id="d2cc0-109">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="d2cc0-110">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="d2cc0-110">External Resources</span></span>  
 [<span data-ttu-id="d2cc0-111">Создание определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="d2cc0-111">Creating a User-Defined Type</span></span>](../../relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types.md)  
  
 [<span data-ttu-id="d2cc0-112">Основные сведения о типах пространственных данных</span><span class="sxs-lookup"><span data-stu-id="d2cc0-112">Spatial Data Types Overview</span></span>](../../relational-databases/spatial/spatial-data-types-overview.md)  
  
  
