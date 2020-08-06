---
title: Отладка кода модулей доставки | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], debugging
- debugging delivery extensions [Reporting Services]
- troubleshooting [Reporting Services], delivery extensions
ms.assetid: a7d959da-5005-4a50-aca7-2cef36aa9947
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb80ac97f5c0e346b208784f1fa5b857ff93ef57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750460"
---
# <a name="debugging-delivery-extension-code"></a><span data-ttu-id="7526e-102">Отладка кода модулей доставки</span><span class="sxs-lookup"><span data-stu-id="7526e-102">Debugging Delivery Extension Code</span></span>
  <span data-ttu-id="7526e-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] предоставляет несколько средств отладки, которые упрощают анализ кода в модуле доставки и поиск ошибок в коде.</span><span class="sxs-lookup"><span data-stu-id="7526e-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your delivery extension code and locate errors in it.</span></span> <span data-ttu-id="7526e-104">Какое средство будет наилучшим, зависит от того, что нужно выполнить.</span><span class="sxs-lookup"><span data-stu-id="7526e-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="7526e-105">В этом примере используется [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7526e-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-delivery-extension-code"></a><span data-ttu-id="7526e-106">Отладка кода в модуле доставки</span><span class="sxs-lookup"><span data-stu-id="7526e-106">To debug your delivery extension code</span></span>  
  
1.  <span data-ttu-id="7526e-107">Запустите среду [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] и откройте проект модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="7526e-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] and open your delivery extension project.</span></span>  
  
2.  <span data-ttu-id="7526e-108">Выполните построение проекта и разверните сборку модуля доставки и сопровождающего ее PDB-файла на сервере отчетов и в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="7526e-108">Build the project and deploy your delivery extension assembly and the accompanying .pdb file to the report server and Report Manager.</span></span> <span data-ttu-id="7526e-109">Дополнительные сведения о развертывании см. в разделе [Развертывание модуля доставки](deploying-a-delivery-extension.md).</span><span class="sxs-lookup"><span data-stu-id="7526e-109">For more information about deployment, see [Deploying a Delivery Extension](deploying-a-delivery-extension.md).</span></span>  
  
3.  <span data-ttu-id="7526e-110">Если создан пользовательский интерфейс подписки, расширяющий диспетчер отчетов, откройте обозреватель Internet Explorer и перейдите к диспетчеру отчетов, оставив код модуля доставки открытым в среде [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7526e-110">If you have written a subscription user interface to extend Report Manager, open Internet Explorer and navigate to Report Manager while leaving your delivery extension code open in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="7526e-111">Если для диспетчера отчетов не развернут пользовательский интерфейс подписки, просто откройте клиентское приложение, из которого можно вызывать модуль доставки по API-интерфейсу SOAP.</span><span class="sxs-lookup"><span data-stu-id="7526e-111">If you do not have a subscription user interface deployed for Report Manager, simply open the client application from which you call your delivery extension using the SOAP API.</span></span>  
  
4.  <span data-ttu-id="7526e-112">Перейдите в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] к проекту модуля доставки и задайте в коде несколько точек останова.</span><span class="sxs-lookup"><span data-stu-id="7526e-112">Navigate to [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] and your delivery extension project, and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="7526e-113">Пока окно с проектом модуля доставки остается активным, выберите в меню **Отладка** команду **Присоединить к процессу**.</span><span class="sxs-lookup"><span data-stu-id="7526e-113">With the delivery extension project still the active window, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="7526e-114">Откроется диалоговое окно **Присоединение к процессу**.</span><span class="sxs-lookup"><span data-stu-id="7526e-114">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="7526e-115">В списке процессов выберите процесс aspnet_wp.exe (или w3wp.exe, если приложение развернуто на сервере IIS 6.0) и нажмите кнопку **Присоединить**.</span><span class="sxs-lookup"><span data-stu-id="7526e-115">From the list of processes, select the aspnet_wp.exe process (or w3wp.exe if your application is deployed on IIS 6.0), and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="7526e-116">Определите новую подписку с помощью модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="7526e-116">Define a new subscription using your delivery extension.</span></span> <span data-ttu-id="7526e-117">Для этого обычно используется диспетчер отчетов или API-интерфейс SOAP.</span><span class="sxs-lookup"><span data-stu-id="7526e-117">You will most likely use Report Manager or the SOAP API.</span></span> <span data-ttu-id="7526e-118">Будет запущен отладчик и начнется выполнение кода с учетом заданных точек останова.</span><span class="sxs-lookup"><span data-stu-id="7526e-118">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="7526e-119">Перемещайтесь по шагам кода с помощью клавиши **F11**.</span><span class="sxs-lookup"><span data-stu-id="7526e-119">Step through your code using the **F11** key.</span></span> <span data-ttu-id="7526e-120">Дополнительные сведения об использовании среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] для отладки см. в документации по среде [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7526e-120">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7526e-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="7526e-121">See Also</span></span>  
 <span data-ttu-id="7526e-122">[Реализация модуля доставки](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="7526e-122">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="7526e-123">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7526e-123">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
