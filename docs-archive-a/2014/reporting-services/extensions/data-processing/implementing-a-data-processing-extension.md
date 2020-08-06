---
title: Реализация модуля обработки данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom data processing extensions [Reporting Services]
- data sources [Reporting Services], data processing extensions
- data processing extensions [Reporting Services]
- extensions [Reporting Services], data processing
ms.assetid: 8dc2b44e-5ad9-411d-a29f-7213e29321a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5a1b7668f2319e742dcf3f1969fc3c5cc85cd7eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750488"
---
# <a name="implementing-a-data-processing-extension"></a><span data-ttu-id="8867c-102">Реализация модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="8867c-102">Implementing a Data Processing Extension</span></span>
  <span data-ttu-id="8867c-103">Модули обработки данных в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] позволяют соединяться с источником данных и получать данные.</span><span class="sxs-lookup"><span data-stu-id="8867c-103">Data processing extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enable you to connect to a data source and retrieve data.</span></span> <span data-ttu-id="8867c-104">Они также служат мостом между источником данных и набором данных.</span><span class="sxs-lookup"><span data-stu-id="8867c-104">They also serve as a bridge between a data source and a dataset.</span></span> <span data-ttu-id="8867c-105">Модули обработки данных [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] построены на наборе интерфейсов поставщиков данных [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8867c-105">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extensions are modeled after a subset of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] data provider interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8867c-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="8867c-106">In This Section</span></span>  
 [<span data-ttu-id="8867c-107">Общие сведения о модулях обработки данных</span><span class="sxs-lookup"><span data-stu-id="8867c-107">Data Processing Extensions Overview</span></span>](data-processing-extensions-overview.md)  
 <span data-ttu-id="8867c-108">Введение в процесс написания пользовательского модуля обработки данных для служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8867c-108">Introduces how to write a custom data processing extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="8867c-109">Подготовка к реализации модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="8867c-109">Preparing to Implement a Data Processing Extension</span></span>](preparing-to-implement-a-data-processing-extension.md)  
 <span data-ttu-id="8867c-110">Описываются интерфейсы, доступные при внедрении модуля обработки данных служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], а также сроки, в которые необходимо произвести внедрение определенных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="8867c-110">Describes the interfaces available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, as well as when you are required to implement a particular interface.</span></span>  
  
 [<span data-ttu-id="8867c-111">Создание библиотеки модулей обработки данных</span><span class="sxs-lookup"><span data-stu-id="8867c-111">Creating a Data Processing Extension Library</span></span>](creating-a-data-processing-extension-library.md)  
 <span data-ttu-id="8867c-112">Описывается процесс присвоения пространства имен модулю обработки данных служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] и процесс компиляции модуля обработки данных в DLL-библиотеку.</span><span class="sxs-lookup"><span data-stu-id="8867c-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension and compiling your data processing extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="8867c-113">Реализация класса Connection для модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="8867c-113">Implementing a Connection Class for a Data Processing Extension</span></span>](implementing-a-connection-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="8867c-114">Описываются атрибуты соединения и методы реализации собственного класса **Connection** для модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="8867c-114">Describes the attributes of a connection and how to implement your own **Connection** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="8867c-115">Реализация класса Command для модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="8867c-115">Implementing a Command Class for a Data Processing Extension</span></span>](implementing-a-command-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="8867c-116">Описываются атрибуты команды и методы реализации собственного класса **Command** для модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="8867c-116">Describes the attributes of a command, and how to implement your own **Command** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="8867c-117">Реализация класса DataReader для модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="8867c-117">Implementing a DataReader Class for a Data Processing Extension</span></span>](implementing-a-datareader-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="8867c-118">Описываются атрибуты модуля чтения данных и методы реализации собственного класса **DataReader** для модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="8867c-118">Describes the attributes of a data reader and how to implement your own **DataReader** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="8867c-119">Использование внешнего набора данных со службами Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8867c-119">Using an External Dataset with Reporting Services</span></span>](using-an-external-dataset-with-reporting-services.md)  
 <span data-ttu-id="8867c-120">Описывается способ предоставления пользовательских объектов **DataSet** для использования сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="8867c-120">Describes how to expose your custom **DataSet** objects to the report server for consumption.</span></span>  
  
 [<span data-ttu-id="8867c-121">Развертывание модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="8867c-121">Deploying a Data Processing Extension</span></span>](deploying-a-data-processing-extension.md)  
 <span data-ttu-id="8867c-122">Описывается процесс развертывания модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="8867c-122">Describes how to deploy your data processing extension.</span></span>  
  
 [<span data-ttu-id="8867c-123">Отладка кода модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="8867c-123">Debugging Data Processing Extension Code</span></span>](debugging-data-processing-extension-code.md)  
 <span data-ttu-id="8867c-124">Описывается процесс отладки кода модулей обработки данных.</span><span class="sxs-lookup"><span data-stu-id="8867c-124">Describes how to debug code in your data processing extensions.</span></span>  
  
 [<span data-ttu-id="8867c-125">Удаление модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="8867c-125">Removing a Data Processing Extension</span></span>](removing-a-data-processing-extension.md)  
 <span data-ttu-id="8867c-126">Описывается процесс удаления модуля обработки данных из сервера отчетов или из конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="8867c-126">Describes how to remove a data processing extension from a report server or Report Designer.</span></span>  
  
 <span data-ttu-id="8867c-127">Образец полностью реализованного модуля обработки данных см. на странице [Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="8867c-127">For a sample of a fully implemented data processing extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8867c-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="8867c-128">See Also</span></span>  
 <span data-ttu-id="8867c-129">[Расширения Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="8867c-129">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="8867c-130">Библиотека модулей служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8867c-130">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
