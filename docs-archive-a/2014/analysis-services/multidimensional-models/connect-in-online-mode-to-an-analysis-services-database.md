---
title: Подключение в режиме "в сети" к базе данных Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, connecting
ms.assetid: 33041234-7106-404f-a289-8e904f32aff2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 363beb7132eae92907198979fe2d9892c5d07b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737103"
---
# <a name="connect-in-online-mode-to-an-analysis-services-database"></a><span data-ttu-id="3af86-102">Подключение в режиме «в сети» к базе данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3af86-102">Connect in Online Mode to an Analysis Services Database</span></span>
  <span data-ttu-id="3af86-103">Можно напрямую подключаться к существующей [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базе данных и изменять объекты непосредственно в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="3af86-103">You can connect directly to an existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and directly modify objects within that database.</span></span> <span data-ttu-id="3af86-104">При прямом подсоединении к базе данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] изменения объектов происходят моментально и проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не создается в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3af86-104">When you connect directly to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, changes to objects occur immediately and no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project is created within [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-connect-directly-to-an-analysis-services-database-by-using-sql-server-data-tools"></a><span data-ttu-id="3af86-105">Прямое соединение с базой данных служб Analysis Services с помощью SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="3af86-105">To Connect Directly to an Analysis Services Database by using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="3af86-106">Откройте среду [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3af86-106">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="3af86-107">В меню **Файл** укажите пункт **Открыть** и выберите пункт **База данных служб Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="3af86-107">On the **File** menu, point to **Open** and then click **Analysis Services Database**.</span></span>  
  
3.  <span data-ttu-id="3af86-108">Выберите **Соединиться с существующей базой данных**.</span><span class="sxs-lookup"><span data-stu-id="3af86-108">Select **Connect to existing database**.</span></span>  
  
4.  <span data-ttu-id="3af86-109">Укажите имя сервера и имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="3af86-109">Specify the server name and the database name.</span></span>  
  
     <span data-ttu-id="3af86-110">Можно либо ввести имя базы данных, либо запросить отображение существующих на сервере баз данных.</span><span class="sxs-lookup"><span data-stu-id="3af86-110">You can either type the database name or query the server to view the existing databases on the server.</span></span>  
  
5.  <span data-ttu-id="3af86-111">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3af86-111">Click **OK**.</span></span>  
  
     <span data-ttu-id="3af86-112">Теперь можно редактировать любой объект непосредственно в базе данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3af86-112">You can now directly edit any objects within the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af86-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="3af86-113">See Also</span></span>  
 <span data-ttu-id="3af86-114">[Работа с Analysis Services проектами и базами данных на этапе разработки](work-with-analysis-services-projects-and-databases-in-development.md) </span><span class="sxs-lookup"><span data-stu-id="3af86-114">[Working with Analysis Services Projects and Databases During the Development Phase](work-with-analysis-services-projects-and-databases-in-development.md) </span></span>  
 [<span data-ttu-id="3af86-115">Создание многомерных моделей с помощью SQL Server Data Tools (SSDT)</span><span class="sxs-lookup"><span data-stu-id="3af86-115">Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;</span></span>](creating-multidimensional-models-using-sql-server-data-tools-ssdt.md)  
  
  
