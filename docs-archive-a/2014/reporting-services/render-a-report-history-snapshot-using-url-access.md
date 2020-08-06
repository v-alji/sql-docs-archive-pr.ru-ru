---
title: Обработка моментального снимка журнала отчета с использованием доступа по URL-адресу | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services], report history
- history snapshots [Reporting Services]
- historical data [Reporting Services]
- snapshots [Reporting Services], URL access
- snapshots [Reporting Services], rendering report history
ms.assetid: 3f87f82d-0e61-4492-9c4b-f5238c39e8cd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 67854a39ab7e38289627d03ac00cc4b2a6dca6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664008"
---
# <a name="render-a-report-history-snapshot-using-url-access"></a><span data-ttu-id="71cc2-102">Обработка моментального снимка журнала отчета с использованием доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="71cc2-102">Render a Report History Snapshot Using URL Access</span></span>
  <span data-ttu-id="71cc2-103">Подготовить отчет к просмотру можно с помощью моментального снимка журнала отчета. Для этого необходимо указать параметр *rs:Snapshot* и присвоить ему значение допустимого идентификатора моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="71cc2-103">You can render a report based on a report history snapshot by supplying the *rs:Snapshot* parameter and setting its value to a valid snapshot ID.</span></span> <span data-ttu-id="71cc2-104">Значение параметра должно указываться в формате ГГГГ-ММ-ДДТЧЧ:ММ:СС согласно стандарту Международной организации по стандартизации (ISO) 8601.</span><span class="sxs-lookup"><span data-stu-id="71cc2-104">The parameter value is in the format YYYY-MM-DDTHH:MM:SS, based on the International Organization for Standardization (ISO) 8601 standard.</span></span>  
  
 <span data-ttu-id="71cc2-105">Если этот параметр не указан, то отчет подготавливается к просмотру согласно параметрам его выполнения и параметрам управления кэшем на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="71cc2-105">If you omit this parameter, the report is rendered according to the report execution and cache management option settings of the report server.</span></span> <span data-ttu-id="71cc2-106">Дополнительные сведения о выполнении отчетов см. в разделе [Установка свойств обработки отчетов](report-server/set-report-processing-properties.md).</span><span class="sxs-lookup"><span data-stu-id="71cc2-106">For more information about report execution, see [Set Report Processing Properties](report-server/set-report-processing-properties.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71cc2-107">Пример</span><span class="sxs-lookup"><span data-stu-id="71cc2-107">Example</span></span>  
 <span data-ttu-id="71cc2-108">В приведенном ниже примере показан URL-адрес, по которому происходит получение моментального снимка журнала отчета.</span><span class="sxs-lookup"><span data-stu-id="71cc2-108">The following example shows a URL that retrieves a report history snapshot:</span></span>  
  
```  
http://myrshost/reportserver?/SampleReports/Company Sales&rs:Snapshot=2003-04-07T13:40:02  
```  
  
## <a name="see-also"></a><span data-ttu-id="71cc2-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="71cc2-109">See Also</span></span>  
 <span data-ttu-id="71cc2-110">[Доступ по URL-адресу (службы SSRS)](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="71cc2-110">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="71cc2-111">Ссылка на параметр доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="71cc2-111">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
