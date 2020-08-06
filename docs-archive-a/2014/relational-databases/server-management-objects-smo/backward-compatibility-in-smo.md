---
title: Обратная совместимость в SMO | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 2f986436-aaf2-4eaf-9809-df849d97d4fb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73b6f4eebccf23850ccf08ec95ccb59dbc5c6293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664135"
---
# <a name="backward-compatibility-in-smo"></a><span data-ttu-id="0d16e-102">Обратная совместимость в SMO</span><span class="sxs-lookup"><span data-stu-id="0d16e-102">Backward Compatibility in SMO</span></span>
  <span data-ttu-id="0d16e-103">Приложения объектов SMO, написанные с помощью предыдущих версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , можно повторно компилировать с помощью объекта SMO в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d16e-103">SMO applications that were written using previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be recompiled by using SMO in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="migrating-smo-applications"></a><span data-ttu-id="0d16e-104">Миграция приложений объектов SMO</span><span class="sxs-lookup"><span data-stu-id="0d16e-104">Migrating SMO Applications</span></span>  
 <span data-ttu-id="0d16e-105">Ссылки на DLL-библиотеки SMO в более ранних версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должны быть удалены, а на их место необходимо вставить ссылки на новые DLL-библиотеки SMO, представленные в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d16e-105">References to SMO dlls in older versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed, and references to the new SMO dlls that are provided with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be included.</span></span>  
  
 <span data-ttu-id="0d16e-106">Необходимо предоставить ссылки, как минимум, на следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="0d16e-106">Minimally, you would reference the following:</span></span>  
  
-   <span data-ttu-id="0d16e-107">Microsoft.SqlServer.ConnectionInfo</span><span class="sxs-lookup"><span data-stu-id="0d16e-107">Microsoft.SqlServer.ConnectionInfo</span></span>  
  
-   <span data-ttu-id="0d16e-108">Microsoft.SqlServer.Smo</span><span class="sxs-lookup"><span data-stu-id="0d16e-108">Microsoft.SqlServer.Smo</span></span>  
  
-   <span data-ttu-id="0d16e-109">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="0d16e-109">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
 <span data-ttu-id="0d16e-110">Эти файлы необходимы для классов соединений, служебных классов SMO и классов SFC.</span><span class="sxs-lookup"><span data-stu-id="0d16e-110">These files are required for connection classes, SMO utility classes, and foundation classes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d16e-111">Файл SmoEnum.dll удален. Ссылка на этот файл должна быть удалена из проекта SMO [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d16e-111">SmoEnum.dll has been removed so references to it must be removed from the SMO [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] project.</span></span>  
  
 <span data-ttu-id="0d16e-112">Пространства имен также были изменены. Воспользуйтесь следующими:</span><span class="sxs-lookup"><span data-stu-id="0d16e-112">The namespaces have also changed, so you can use the following:</span></span>  
  
##### <a name="for-visual-c"></a><span data-ttu-id="0d16e-113">Для Visual C#</span><span class="sxs-lookup"><span data-stu-id="0d16e-113">For Visual C#</span></span>  
  
```  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
```  
  
##### <a name="for-visual-basic"></a><span data-ttu-id="0d16e-114">Для Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0d16e-114">For Visual Basic</span></span>  
  
```  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
```  
  
 <span data-ttu-id="0d16e-115">Если в коде используется функциональность URN типа `Server.GetSqlSmoObject(Urn)`, необходимо установить связь с пространством имен Microsoft.SqlServer.Management.Sdk.Sfc.</span><span class="sxs-lookup"><span data-stu-id="0d16e-115">If your code uses Urn functionality, such as `Server.GetSqlSmoObject(Urn)`, you must link to the Microsoft.SqlServer.Management.Sdk.Sfc namespace.</span></span>  
  
 <span data-ttu-id="0d16e-116">Если данный код использует передачу объектов непосредственно, необходимо установить связь с пространством имен Microsoft.SqlServer.Management.SmoExtended.</span><span class="sxs-lookup"><span data-stu-id="0d16e-116">If your code uses the Transfer object directly, you will have to link to the Microsoft.SqlServer.Management.SmoExtended namespace.</span></span>  
  
 <span data-ttu-id="0d16e-117">В случае выполнения миграции кода, может понадобиться изменение кода.</span><span class="sxs-lookup"><span data-stu-id="0d16e-117">When you migrate code, you might have to modify the code.</span></span> <span data-ttu-id="0d16e-118">Это происходит потому, что некоторые функции [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]устарели.</span><span class="sxs-lookup"><span data-stu-id="0d16e-118">This is because several [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] features have been deprecated in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="0d16e-119">Дополнительные сведения об устаревших функциях см. в разделе [устаревшие ядро СУБД функции в SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] электронной документации по.</span><span class="sxs-lookup"><span data-stu-id="0d16e-119">For more information about deprecated features, see [Deprecated Database Engine Features in SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
