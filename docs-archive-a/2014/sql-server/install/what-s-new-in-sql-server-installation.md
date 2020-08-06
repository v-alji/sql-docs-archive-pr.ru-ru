---
title: Новые возможности установки SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- installing SQL Server, what's new
- SQL Server, what's new
- SQL Server, installing
ms.assetid: c8642a96-3a09-4ec7-a9c3-c539147e6330
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d34085e320cd8ca0b82d382d6d49eaa303086114
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659102"
---
# <a name="what39s-new-in-sql-server-installation"></a><span data-ttu-id="60d0b-102">Новые возможности установки SQL Server</span><span class="sxs-lookup"><span data-stu-id="60d0b-102">What&#39;s New in SQL Server Installation</span></span>
  <span data-ttu-id="60d0b-103">Windows Vista не является поддерживаемой операционной системой для [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60d0b-103">Windows Vista is not a supported operating system for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span> <span data-ttu-id="60d0b-104">Пакет обновления 1 (SP1) остается минимальным требованием для операционных систем [!INCLUDE[win7](../../includes/win7-md.md)] и [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60d0b-104">Service Pack 1 remains as the minimum requirement for [!INCLUDE[win7](../../includes/win7-md.md)] and [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] operating systems.</span></span> <span data-ttu-id="60d0b-105">Дополнительные сведения о требованиях к операционной системе см. в разделе [требования к оборудованию и программному обеспечению для установки SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="60d0b-105">For more information on operating system requirements, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
 <span data-ttu-id="60d0b-106">При установке [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] будет предложено указать каталог для сохранения извлеченного пакета.</span><span class="sxs-lookup"><span data-stu-id="60d0b-106">Installation of [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] will prompt you to specify the directory to save the extracted package.</span></span> <span data-ttu-id="60d0b-107">Если местоположение не указано, то [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] будет использовать системный диск компьютера как значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="60d0b-107">If no location is entered, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] will default to the computer's system drive.</span></span> <span data-ttu-id="60d0b-108">Извлеченные файлы после завершения установки [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] останутся на диске.</span><span class="sxs-lookup"><span data-stu-id="60d0b-108">The extracted files will remain after [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] installation is complete.</span></span>  
  
 <span data-ttu-id="60d0b-109">В [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] SysPrep поддерживается для всех установок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60d0b-109">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], SysPrep is supported for all installations of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="60d0b-110">SysPrep теперь поддерживает установки кластеров отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="60d0b-110">SysPrep now supports failover cluster installations.</span></span> <span data-ttu-id="60d0b-111">Дополнительные сведения см. в разделе [рекомендации по установке SQL Server с помощью Sysprep](../../database-engine/install-windows/considerations-for-installing-sql-server-using-sysprep.md) и [установке SQL Server 2014 с помощью Sysprep](../../database-engine/install-windows/install-sql-server-using-sysprep.md).</span><span class="sxs-lookup"><span data-stu-id="60d0b-111">For more information, see [Considerations for Installing SQL Server Using SysPrep](../../database-engine/install-windows/considerations-for-installing-sql-server-using-sysprep.md) and [Install SQL Server 2014 Using SysPrep](../../database-engine/install-windows/install-sql-server-using-sysprep.md).</span></span>  
  
 <span data-ttu-id="60d0b-112">Обновление от [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] поддерживается, но не поддерживается параллельная установка.</span><span class="sxs-lookup"><span data-stu-id="60d0b-112">Upgrade from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] is supported, but side-by-side is not supported.</span></span> <span data-ttu-id="60d0b-113">Дополнительные сведения о поддержке [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] в [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]см. в разделе [Поддерживаемые обновления версий и выпусков](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="60d0b-113">For more information about [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] support in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], see [Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span></span>  
  
 <span data-ttu-id="60d0b-114">Начиная с версии [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], компонент Database Engine в выпусках Standard имеет объем памяти 128 ГБ.</span><span class="sxs-lookup"><span data-stu-id="60d0b-114">Beginning in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], the database engine in the Standard edition has a memory capacity of 128 GB.</span></span> <span data-ttu-id="60d0b-115">В [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ядро СУБД в выпусках Standard имело объем памяти 64 ГБ.</span><span class="sxs-lookup"><span data-stu-id="60d0b-115">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the database engine in the Standard edition had a memory capacity of 64 GB.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d0b-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="60d0b-116">See Also</span></span>  
 <span data-ttu-id="60d0b-117">[Новые возможности SQL Server 2014](../what-s-new-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="60d0b-117">[What's New in SQL Server 2014](../what-s-new-in-sql-server-2016.md) </span></span>  
 <span data-ttu-id="60d0b-118">[Спецификации продуктов для SQL Server 2014](../../../2014/getting-started/sql-server-2014-product-specifications.md) </span><span class="sxs-lookup"><span data-stu-id="60d0b-118">[Product Specifications for SQL Server 2014](../../../2014/getting-started/sql-server-2014-product-specifications.md) </span></span>  
 <span data-ttu-id="60d0b-119">[Планирование установки SQL Server](../../../2014/sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="60d0b-119">[Planning a SQL Server Installation](../../../2014/sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="60d0b-120">Требования к аппаратному и программному обеспечению для установки SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="60d0b-120">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
  
