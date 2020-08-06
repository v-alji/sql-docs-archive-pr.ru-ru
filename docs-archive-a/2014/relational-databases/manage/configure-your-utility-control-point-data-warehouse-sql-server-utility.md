---
title: Настройка хранилища данных для точки управления служебной программой (служебная программа SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c2c6f050-8cdb-4b8e-ad38-4aae0a949847
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60b9623b468f2763cf619c325412373e3603f3a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656404"
---
# <a name="configure-your-utility-control-point-data-warehouse-sql-server-utility"></a><span data-ttu-id="75732-102">Настройка хранилища данных точки управления служебной программы (служебная программа SQL Server)</span><span class="sxs-lookup"><span data-stu-id="75732-102">Configure Your Utility Control Point Data Warehouse (SQL Server Utility)</span></span>
  <span data-ttu-id="75732-103">Данные, собранные управляемыми экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , хранятся в хранилище данных управления для программы (UMDW), имя файла UMDW — sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="75732-103">Data collected by managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are stored in the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="75732-104">Можно задать сроком хранения данных в UMDW.</span><span class="sxs-lookup"><span data-stu-id="75732-104">You can configure the UMDW data retention period.</span></span> <span data-ttu-id="75732-105">Дополнительные сведения см. в статье [Администрирование программ (служебная программа SQL Server)](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="75732-105">For more information, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="75732-106">Перечисленные далее параметры конфигурации не могут быть изменены в этой версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75732-106">The following configuration settings are not configurable in this release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="75732-107">Имя UMDW: Sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="75732-107">UMDW name: Sysutility_mdw.</span></span>  
  
-   <span data-ttu-id="75732-108">Частота передачи набора элементов сбора: каждые 15 минут.</span><span class="sxs-lookup"><span data-stu-id="75732-108">Collection set upload frequency: Every 15 minutes.</span></span>  
  
 <span data-ttu-id="75732-109">Каталог UMDW можно настроить: \<System drive>:\Program Files\Microsoft SQL Server\MSSQL10_50.<имя_UCP>\MSSQL\Data\\, где \<System drive> — это чаще всего диск C:\.</span><span class="sxs-lookup"><span data-stu-id="75732-109">The UMDW directory is configurable: \<System drive>:\Program Files\Microsoft SQL Server\MSSQL10_50.<UCP_Name>\MSSQL\Data\\, where \<System drive> is normally the C:\ drive.</span></span> <span data-ttu-id="75732-110">Файл журнала Sysutility_mdw_\<GUID>_LOG находится в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="75732-110">The log file, Sysutility_mdw_\<GUID>_LOG, is located in the same directory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75732-111">Расположение файла UMDW (sysutility_mdw) можно изменить путем отсоединения и присоединения или с помощью инструкции ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="75732-111">The UMDW (sysutility_mdw) file location can be changed using detach/attach or ALTER DATABASE.</span></span> <span data-ttu-id="75732-112">Рекомендуется использовать инструкцию ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="75732-112">We recommend the use of ALTER DATABASE.</span></span> <span data-ttu-id="75732-113">Дополнительные сведения см. в разделе [ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="75732-113">For more information see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75732-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="75732-114">See Also</span></span>  
 [<span data-ttu-id="75732-115">Функции и задачи служебной программы SQL Server</span><span class="sxs-lookup"><span data-stu-id="75732-115">SQL Server Utility Features and Tasks</span></span>](sql-server-utility-features-and-tasks.md)  
  
  
