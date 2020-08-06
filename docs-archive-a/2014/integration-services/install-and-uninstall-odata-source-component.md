---
title: Установка и удаление компонента источника OData | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0a3ae788-e8c8-4a4d-bb15-34c673abcd17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fad0a86c6226f408b0495569d0a853dd7340aeca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664409"
---
# <a name="install-and-uninstall-odata-source-component"></a><span data-ttu-id="7b1d6-102">Установка и удаление компонента источника OData</span><span class="sxs-lookup"><span data-stu-id="7b1d6-102">Install and Uninstall OData Source Component</span></span>
  <span data-ttu-id="7b1d6-103">В этом разделе приведены инструкции по установке или удалению компонента источника OData на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7b1d6-103">This topic provides instructions for installing or removing OData Source Component on your computer.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="7b1d6-104">Установка</span><span class="sxs-lookup"><span data-stu-id="7b1d6-104">Installation</span></span>  
 <span data-ttu-id="7b1d6-105">Для компонента источника OData на компьютере должны быть установлены следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="7b1d6-105">The OData Source Component requires following prerequisite components to be installed on your computer.</span></span>  
  
-   <span data-ttu-id="7b1d6-106">SQL Server Data Tools (для проектирования пакетов)</span><span class="sxs-lookup"><span data-stu-id="7b1d6-106">SQL Server Data Tools (to design packages)</span></span>  
  
-   <span data-ttu-id="7b1d6-107">Службы SQL Server Integration Services (для запуска пакетов вне Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="7b1d6-107">SQL Server Integration Services (to run packages outside Visual Studio)</span></span>  
  
 <span data-ttu-id="7b1d6-108">Чтобы установить компонент источника OData, загрузите [пакет дополнительных компонентов SQL Server 2014](https://go.microsoft.com/fwlink/p/?LinkId=391999) и запустите один из следующих MSI-файлов.</span><span class="sxs-lookup"><span data-stu-id="7b1d6-108">To install the OData Source Component, download [SQL Server 2014 Feature Pack](https://go.microsoft.com/fwlink/p/?LinkId=391999) and run one of the following MSI files.</span></span>  
  
-   <span data-ttu-id="7b1d6-109">ODataSourceForSQLServer2014-amd64.msi для 64-разрядных платформ</span><span class="sxs-lookup"><span data-stu-id="7b1d6-109">ODataSourceForSQLServer2014-amd64.msi for 64bit platforms</span></span>  
  
-   <span data-ttu-id="7b1d6-110">ODataSourceForSQLServer2014-x86.msi для 32-разрядных платформ</span><span class="sxs-lookup"><span data-stu-id="7b1d6-110">ODataSourceForSQLServer2014-x86.msi for 32bit platforms</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7b1d6-111">64-разрядный установщик устанавливает 32-разрядную и 64-разрядную версии компонента источника OData.</span><span class="sxs-lookup"><span data-stu-id="7b1d6-111">The 64bit installer will install both 32bit and 64bit versions of the OData Source Component.</span></span> <span data-ttu-id="7b1d6-112">Если используется 32-разрядная ОС, необходимо запускать 32-разрядный установщик.</span><span class="sxs-lookup"><span data-stu-id="7b1d6-112">You only need to run the 32bit installer if you are using a 32bit OS.</span></span>  
  
## <a name="uninstallation"></a><span data-ttu-id="7b1d6-113">Удаление</span><span class="sxs-lookup"><span data-stu-id="7b1d6-113">Uninstallation</span></span>  
 <span data-ttu-id="7b1d6-114">Компонент источника OData можно удалить в меню **Программы и компоненты** .</span><span class="sxs-lookup"><span data-stu-id="7b1d6-114">The OData Source component can be uninstalled from the **Programs and Features** menu.</span></span> <span data-ttu-id="7b1d6-115">Найдите элемент **Компонент источника OData Microsoft SQL Server SSIS (x64)** и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7b1d6-115">Find the **Microsoft SQL Server SSIS OData Source Component (x64)** entry and click **Uninstall**.</span></span>  
  
  
