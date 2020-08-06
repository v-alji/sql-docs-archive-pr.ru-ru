---
title: Рекомендации по запуску служебной программы и наборов элементов сбора, не являющихся служебными программами, на одном экземпляре SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ca7ee9b3-ef9a-4ba4-83d0-9ee9f80dab27
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67df2d65cc9da4026377e77c152c0d78f3749932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665330"
---
# <a name="considerations-for-running-utility-and-non-utility-collection-sets-on-the-same-instance-of-sql-server"></a><span data-ttu-id="65cce-102">Замечания по выполнению программы, не относящиеся к прочим наборам элементов сбора на том же экземпляре SQL Server</span><span class="sxs-lookup"><span data-stu-id="65cce-102">Considerations for Running Utility and non-Utility Collection Sets on the Same Instance of SQL Server</span></span>
  <span data-ttu-id="65cce-103">Набор элементов сбора служебной программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживается параллельно с наборами элементов сбора, не касающимися служебной программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65cce-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection set is supported side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="65cce-104">Таким образом, управляемый экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно наблюдать по другим наборам элементов сбора, поскольку он является элементом служебной программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65cce-104">That is, a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be monitored by other collection sets while it is a member of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="65cce-105">Однако при регистрации экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в программе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] все функции сбора данных, не относящиеся к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , должны быть отключены.</span><span class="sxs-lookup"><span data-stu-id="65cce-105">However, you must disable non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection functionality while the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is being enrolled into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
 <span data-ttu-id="65cce-106">После регистрации экземпляра в UCP наборы элементов сбора, не относящиеся к служебной программе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , можно будет перезапустить.</span><span class="sxs-lookup"><span data-stu-id="65cce-106">After the instance is enrolled with the UCP, you can restart non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="65cce-107">Следует, однако, отметить, что все наборы элементов сбора, находящиеся в управляемом экземпляре, передают свои данные в хранилище данных управления для программы (UMDW).</span><span class="sxs-lookup"><span data-stu-id="65cce-107">Note, however, that all collection sets on the managed instance will upload their data to the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="65cce-108">Чтобы наборы элементов сбора служебной программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] работали параллельно с наборами элементов сбора, не относящимися к служебной программе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , необходимо учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="65cce-108">To run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets, consider the following points:</span></span>  
  
-   <span data-ttu-id="65cce-109">Поддерживается параллельная работа наборов элементов сбора.</span><span class="sxs-lookup"><span data-stu-id="65cce-109">Side-by-side collection sets are supported.</span></span>  
  
-   <span data-ttu-id="65cce-110">Существующие сборщики данных необходимо отключать при регистрации экземпляров в программе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65cce-110">You must disable existing data collectors while enrolling instances into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
-   <span data-ttu-id="65cce-111">Чтобы передать требования проверки, перед созданием UCP, а также перед регистрацией экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в программе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо запустить следующие хранимые процедуры:</span><span class="sxs-lookup"><span data-stu-id="65cce-111">To pass validation requirements, you must run the following stored procedures on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you create a UCP, and on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you enroll it into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility:</span></span>  
  
    ```  
    exec msdb.dbo.sp_syscollector_set_warehouse_database_name NULL  
    exec msdb.dbo.sp_syscollector_set_warehouse_instance_name NULL  
    ```  
  
     <span data-ttu-id="65cce-112">Если не запустить эти хранимые процедуры перед запуском мастера создания UCP или мастера добавления управляемого экземпляра, то операция завершится неудачей.</span><span class="sxs-lookup"><span data-stu-id="65cce-112">If you do not run these stored procedures before you launch the Create UCP Wizard or Add Managed Instance Wizard, the operation will fail.</span></span>  
  
-   <span data-ttu-id="65cce-113">Для всех наборов элементов сбора в управляемом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо использовать хранилище UMDW (sysutility_mdw) служебной программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65cce-113">You must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility UMDW (sysutility_mdw) for all collection sets on a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65cce-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="65cce-114">See Also</span></span>  
 <span data-ttu-id="65cce-115">[Функции и задачи служебной программы SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="65cce-115">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="65cce-116">Настройка хранилища данных точки управления служебной программы (служебная программа SQL Server)</span><span class="sxs-lookup"><span data-stu-id="65cce-116">Configure Your Utility Control Point Data Warehouse &#40;SQL Server Utility&#41;</span></span>](configure-your-utility-control-point-data-warehouse-sql-server-utility.md)  
  
  
