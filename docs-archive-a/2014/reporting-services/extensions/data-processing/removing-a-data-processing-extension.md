---
title: Удаление модуля обработки данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting data processing extensions
- data processing extensions [Reporting Services], removing
- removing data processing extensions
ms.assetid: 1d89e32b-0631-44f6-8178-a57fb791d26d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f5dfd3a6a7615fa3fd91c917bba6dbf0808f0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750483"
---
# <a name="removing-a-data-processing-extension"></a><span data-ttu-id="50971-102">Удаление модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="50971-102">Removing a Data Processing Extension</span></span>
  <span data-ttu-id="50971-103">Чтобы удалить модуль обработки данных, просто удалите элемент **Extension** для модуля обработки данных в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="50971-103">To remove a data processing extension, simply remove the **Extension** element for your data processing extension from the configuration file.</span></span> <span data-ttu-id="50971-104">Если выполнены записи для сервера отчетов, а также для конструктора отчетов, удалите элемент **Extension** из файла RSReportServer.config и из файла RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="50971-104">If you made entries for a report server as well as Report Designer, remove the **Extension** element from both the RSReportServer.config and RSReportDesigner.config files.</span></span> <span data-ttu-id="50971-105">После удаления сведений о конфигурации модуль обработки данных становится недоступным компоненту.</span><span class="sxs-lookup"><span data-stu-id="50971-105">After the configuration information is removed, the data processing extension is no longer available to the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50971-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="50971-106">See Also</span></span>  
 <span data-ttu-id="50971-107">[Расширения Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="50971-107">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="50971-108">[Реализация модуля обработки данных](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="50971-108">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="50971-109">Библиотека модулей служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="50971-109">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
