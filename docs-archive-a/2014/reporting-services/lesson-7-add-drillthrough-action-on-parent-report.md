---
title: Занятие 7. Добавление операции детализации к родительскому отчету | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aad2da1a-d7b1-4afa-a66a-1ff102e8306f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62773f78e5aeee9e60dc82aec3d48bcf1a0eae8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668087"
---
# <a name="lesson-7-add-drillthrough-action-on-parent-report"></a><span data-ttu-id="86eee-102">Занятие 7. Добавление операции детализации к родительскому отчету</span><span class="sxs-lookup"><span data-stu-id="86eee-102">Lesson 7: Add Drillthrough Action on Parent Report</span></span>
  <span data-ttu-id="86eee-103">После добавления элемента управления ReportViewer в приложение веб-сайта далее необходимо добавить действие детализации в родительский отчет.</span><span class="sxs-lookup"><span data-stu-id="86eee-103">After you add a ReportViewer control to the website application, your next step is to add a drillthrough action on the parent report.</span></span>  
  
### <a name="to-add-drillthrough-action-on-the-parent-report"></a><span data-ttu-id="86eee-104">Добавление действия детализации в родительский отчет</span><span class="sxs-lookup"><span data-stu-id="86eee-104">To add drillthrough action on the parent report</span></span>  
  
1.  <span data-ttu-id="86eee-105">Перейдите к родительскому отчету.</span><span class="sxs-lookup"><span data-stu-id="86eee-105">Go to the parent report.</span></span>  
  
2.  <span data-ttu-id="86eee-106">Щелкните текстовое поле, в котором содержится значение **Имя**.</span><span class="sxs-lookup"><span data-stu-id="86eee-106">Click the textbox that holds the value of **Name**.</span></span>  
  
3.  <span data-ttu-id="86eee-107">Щелкните это текстовое поле правой кнопкой мыши и выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="86eee-107">Right click the textbox, and then click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="86eee-108">Перейдите на вкладку **Действие** и выберите параметр **Переход к отчету** .</span><span class="sxs-lookup"><span data-stu-id="86eee-108">Go to the **Action** tab, and then select the **Go to report** option.</span></span>  
  
5.  <span data-ttu-id="86eee-109">В разделе **Указать отчет** введите имя дочернего отчета.</span><span class="sxs-lookup"><span data-stu-id="86eee-109">Enter the name of the child report in the **Specify a report** section.</span></span>  
  
6.  <span data-ttu-id="86eee-110">В разделе **Использование этих параметров для выполнения отчета** нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="86eee-110">Click **Add** under **Use these parameters to run the report** section.</span></span>  
  
7.  <span data-ttu-id="86eee-111">Введите **productid** в поле **Имя** , затем выберите пункт **ProductID** в раскрывающемся списке **Значение** .</span><span class="sxs-lookup"><span data-stu-id="86eee-111">Type **productid** in the **name** box, and then click **ProductID** in the **Value** drop-down list.</span></span>  
  
8.  <span data-ttu-id="86eee-112">Нажмите кнопку **ОК** для завершения.</span><span class="sxs-lookup"><span data-stu-id="86eee-112">Click **Ok** to finish.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="86eee-113">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="86eee-113">Next Task</span></span>  
 <span data-ttu-id="86eee-114">Тем самым в родительский отчет была успешно добавлена операция детализации.</span><span class="sxs-lookup"><span data-stu-id="86eee-114">You have successfully added a drillthrough action on the parent report.</span></span> <span data-ttu-id="86eee-115">Затем необходимо создать фильтр данных для таблицы данных, которая определена в дочернем отчете.</span><span class="sxs-lookup"><span data-stu-id="86eee-115">Next, you will create a data filter for the data table that you defined for the child report.</span></span>  
  
  
