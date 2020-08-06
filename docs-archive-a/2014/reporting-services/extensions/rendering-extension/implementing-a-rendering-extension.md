---
title: Реализация модуля подготовки отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendering extensions [Reporting Services]
- custom rendering extensions [Reporting Services]
- transformations [Reporting Services]
- extensions [Reporting Services], rendering
- rendering extensions [Reporting Services], implementing
ms.assetid: 4a5c64f5-2391-4597-ba3f-81d265b23703
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 03deb7c818de8d875f69b585ae6015fc178e707d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664750"
---
# <a name="implementing-a-rendering-extension"></a><span data-ttu-id="d72d3-102">Реализация модуля подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="d72d3-102">Implementing a Rendering Extension</span></span>
  <span data-ttu-id="d72d3-103">Модуль подготовки отчетов – это компонент или модуль сервера отчетов, преобразующий данные отчета и сведения о макете в формат, определяемый устройством отображения.</span><span class="sxs-lookup"><span data-stu-id="d72d3-103">A rendering extension is a component or module of a report server that transforms report data and layout information into a device-specific format.</span></span> <span data-ttu-id="d72d3-104">Службы SQL Server Reporting Services включают шесть модулей подготовки отчетов: HTML, Excel, Word, CSV или текст, XML, изображения и PDF.</span><span class="sxs-lookup"><span data-stu-id="d72d3-104">SQL Server Reporting Services includes six rendering extensions: HTML, Excel, Word, CSV or Text, XML, Image, and PDF.</span></span> <span data-ttu-id="d72d3-105">Можно создать дополнительные модули подготовки для создания отчетов в других форматах.</span><span class="sxs-lookup"><span data-stu-id="d72d3-105">You can create additional rendering extensions to generate reports in other formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d72d3-106">Чтобы определить доступные модули подготовки отчетов, можно просмотреть список установленных модулей подготовки отчетов в файле RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="d72d3-106">To determine which rendering extensions are available, you can view the list of installed extensions in the RSReportServer.config file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d72d3-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d72d3-107">In This Section</span></span>  
 [<span data-ttu-id="d72d3-108">Общие сведения о модулях подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="d72d3-108">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
 <span data-ttu-id="d72d3-109">Представляет способ написания пользовательских модулей подготовки отчетов для служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d72d3-109">Introduces how to write a custom rendering extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="d72d3-110">Реализация интерфейса IRenderingExtension</span><span class="sxs-lookup"><span data-stu-id="d72d3-110">Implementing the IRenderingExtension Interface</span></span>](implementing-the-irenderingextension-interface.md)  
 <span data-ttu-id="d72d3-111">Описывает атрибуты модуля подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="d72d3-111">Describes the attributes of a rendering extension.</span></span>  
  
 [<span data-ttu-id="d72d3-112">Развертывание модуля подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="d72d3-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
 <span data-ttu-id="d72d3-113">Описывает способ развертывания модуля подготовки отчетов на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="d72d3-113">Describes how to deploy a rendering extension on a report server.</span></span>  
  
 [<span data-ttu-id="d72d3-114">Удаление модуля подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="d72d3-114">Removing a Rendering Extension</span></span>](removing-a-rendering-extension.md)  
 <span data-ttu-id="d72d3-115">Описывает способ удаления модуля подготовки отчетов с сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="d72d3-115">Describes how to remove a rendering extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d72d3-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="d72d3-116">See Also</span></span>  
 <span data-ttu-id="d72d3-117">[Модули служб Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="d72d3-117">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="d72d3-118">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d72d3-118">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
