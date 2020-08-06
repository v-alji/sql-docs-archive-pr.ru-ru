---
title: 'Занятие 6. Запуск приложения схемы языка определения отчетов (VB-C #) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a2cd2386-2df8-4b69-ab81-9ad1a31f6d27
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 5a0fc2cd9c12b4b1602f517dc215ca44e686c663
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727490"
---
# <a name="lesson-6-run-the-rdl-schema-application-vb-c"></a><span data-ttu-id="8b549-102">Занятие 6. Запуск приложения схемы языка определения отчетов (VB-C #)</span><span class="sxs-lookup"><span data-stu-id="8b549-102">Lesson 6: Run the RDL Schema Application (VB-C#)</span></span>
  <span data-ttu-id="8b549-103">В среде [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] доступно два способа построения и выполнения приложения командной строки из интегрированной среды разработки:</span><span class="sxs-lookup"><span data-stu-id="8b549-103">[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] offers two methods to build and run a console application from the integrated development environment (IDE):</span></span>  
  
-   <span data-ttu-id="8b549-104">запустить (с отладкой);</span><span class="sxs-lookup"><span data-stu-id="8b549-104">Start (with Debugging)</span></span>  
  
-   <span data-ttu-id="8b549-105">запустить без отладки.</span><span class="sxs-lookup"><span data-stu-id="8b549-105">Start without Debugging</span></span>  
  
### <a name="to-build-and-run-the-samplerdlschema-application"></a><span data-ttu-id="8b549-106">Сборка и запуск приложения SampleRDLSchema</span><span class="sxs-lookup"><span data-stu-id="8b549-106">To build and run the SampleRDLSchema application</span></span>  
  
1.  <span data-ttu-id="8b549-107">В меню **Отладка** выберите команду **Запуск без отладки**.</span><span class="sxs-lookup"><span data-stu-id="8b549-107">From the **Debug** menu, click **Start Without Debugging**.</span></span> <span data-ttu-id="8b549-108">При выборе этой команды окно консоли останется открытым после того, как программа завершит свою работу.</span><span class="sxs-lookup"><span data-stu-id="8b549-108">This ensures that the console window remains open after the program has finished executing.</span></span>  
  
     <span data-ttu-id="8b549-109">Приложение выводит на консоль следующие данные:</span><span class="sxs-lookup"><span data-stu-id="8b549-109">The application prints the following output to the console:</span></span>  
  
    ```  
    Loading Report Definition  
    Updating Report Definition  
    - Old Description: <Old Report Description>  
    - New Description: <New Report Description>  
    Publishing Report Definition  
    ```  
  
2.  <span data-ttu-id="8b549-110">Чтобы закрыть консоль, нажмите любую кнопку.</span><span class="sxs-lookup"><span data-stu-id="8b549-110">Press any key to close the console.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8b549-111">Сведения обо всех возникающих ошибках выводятся на консоль.</span><span class="sxs-lookup"><span data-stu-id="8b549-111">Any errors that occur are written to the console.</span></span>  
  
3.  <span data-ttu-id="8b549-112">Когда образец приложения закончит выполнение, на сервере отчетов будет сохранена обновленная копия отчета.</span><span class="sxs-lookup"><span data-stu-id="8b549-112">When the sample application is finished running an updated copy of the report will be saved to the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b549-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b549-113">See Also</span></span>  
 <span data-ttu-id="8b549-114">[Обновление отчетов с использованием классов, созданных из учебника по схеме языка определения отчетов &#40;SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="8b549-114">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="8b549-115">Язык определения отчетов (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="8b549-115">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
