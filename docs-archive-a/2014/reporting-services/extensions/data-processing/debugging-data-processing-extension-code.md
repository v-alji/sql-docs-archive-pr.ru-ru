---
title: Отладка кода модуля обработки данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- debugging data processing extensions [Reporting Services]
- troubleshooting [Reporting Services], data processing extensions
- data processing extensions [Reporting Services], debugging
ms.assetid: e963e205-9ae0-446d-97df-028a1d2727d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bf7490145f91ee8b3cfc2357c34010bed593ed9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658652"
---
# <a name="debugging-data-processing-extension-code"></a><span data-ttu-id="44cb8-102">Отладка кода модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="44cb8-102">Debugging Data Processing Extension Code</span></span>
  <span data-ttu-id="44cb8-103">Платформа [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] предоставляет несколько средств отладки, которые помогают анализировать код в модуле обработки данных и искать в нем ошибки.</span><span class="sxs-lookup"><span data-stu-id="44cb8-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your data processing extension code and locate errors in it.</span></span> <span data-ttu-id="44cb8-104">Какое средство будет наилучшим, зависит от того, что нужно выполнить.</span><span class="sxs-lookup"><span data-stu-id="44cb8-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="44cb8-105">В этом примере используется [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44cb8-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-data-processing-extension-code"></a><span data-ttu-id="44cb8-106">Отладка кода модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="44cb8-106">To debug your data processing extension code</span></span>  
  
1.  <span data-ttu-id="44cb8-107">Запустите среду [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] и откройте проект модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="44cb8-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)], and open your data processing extension project.</span></span>  
  
2.  <span data-ttu-id="44cb8-108">Постройте проект и разверните в конструкторе отчетов сборку модуля обработки данных и сопроводительный PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="44cb8-108">Build the project, and deploy your data processing extension assembly and the accompanying .pdb file to the Report Designer.</span></span> <span data-ttu-id="44cb8-109">Дополнительные сведения о развертывании см. в статье [Практическое руководство. Развертывание модуля обработки данных в конструкторе отчетов](deploying-a-data-processing-extension-to-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="44cb8-109">For more information about deployment, see [How to: Deploy a Data Processing Extension to Report Designer](deploying-a-data-processing-extension-to-report-designer.md).</span></span>  
  
3.  <span data-ttu-id="44cb8-110">Откройте новый проект отчета в среде [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], оставив код модуля обработки данных открытым в отдельном окне среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44cb8-110">Open a new Report Project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] while leaving your data processing extension code open in a separate window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>  
  
4.  <span data-ttu-id="44cb8-111">Перейдите к окну среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], содержащему проект модуля обработки данных, и установите в коде несколько точек останова.</span><span class="sxs-lookup"><span data-stu-id="44cb8-111">Navigate to the window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] that contains your data processing extension project and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="44cb8-112">Пока окно с проектом модуля обработки данных остается активным, в меню **Отладка** выберите команду **Присоединить к процессу**.</span><span class="sxs-lookup"><span data-stu-id="44cb8-112">With the data processing extension project window still active, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="44cb8-113">Откроется диалоговое окно **Присоединение к процессу**.</span><span class="sxs-lookup"><span data-stu-id="44cb8-113">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="44cb8-114">Выберите из списка процессов devenv.exe, который соответствует проекту отчета, и нажмите кнопку **Присоединить**.</span><span class="sxs-lookup"><span data-stu-id="44cb8-114">From the list of processes, select the devenv.exe process that corresponds to your Report Project and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="44cb8-115">Определите источник данных отчета на вкладке **Данные отчета** в проекте отчета.</span><span class="sxs-lookup"><span data-stu-id="44cb8-115">Define your report data source using the **Report Data** tab of the Report Project.</span></span> <span data-ttu-id="44cb8-116">Чтобы выполнить запрос к пользовательскому источнику данных, скорее всего, будет использоваться обычный конструктор запросов.</span><span class="sxs-lookup"><span data-stu-id="44cb8-116">You will most likely use the generic Query Designer to execute a query against your custom data source.</span></span> <span data-ttu-id="44cb8-117">Будет запущен отладчик и начнется выполнение кода с учетом заданных точек останова.</span><span class="sxs-lookup"><span data-stu-id="44cb8-117">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="44cb8-118">Перемещайтесь по шагам кода с помощью клавиши F11.</span><span class="sxs-lookup"><span data-stu-id="44cb8-118">Step through your code using the F11 key.</span></span> <span data-ttu-id="44cb8-119">Дополнительные сведения об использовании среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] для отладки см. в документации по среде [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44cb8-119">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44cb8-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="44cb8-120">See Also</span></span>  
 <span data-ttu-id="44cb8-121">[Развертывание модуля обработки данных](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="44cb8-121">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="44cb8-122">[Модули служб Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="44cb8-122">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="44cb8-123">[Реализация модуля обработки данных](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="44cb8-123">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="44cb8-124">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="44cb8-124">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
