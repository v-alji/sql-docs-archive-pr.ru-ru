---
title: Занятие 9. Сборка и запуск приложения | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f52d3f3a-0b09-4b34-9112-0b3655271587
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 068deb075f0f60dde634ac29f6f8f934448dc6a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656219"
---
# <a name="lesson-9-build-and-run-the-application"></a><span data-ttu-id="c45f3-102">Lesson 9: Build and Run the Application</span><span class="sxs-lookup"><span data-stu-id="c45f3-102">Lesson 9: Build and Run the Application</span></span>
  <span data-ttu-id="c45f3-103">После создания фильтра данных для таблицы данных далее необходимо построить и запустить приложение веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="c45f3-103">After you create a data filter for the data table, your next step is to build and run the website application.</span></span>

### <a name="to-build-and-run-the-application"></a><span data-ttu-id="c45f3-104">Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="c45f3-104">To build and run the application</span></span>

1.  <span data-ttu-id="c45f3-105">Нажмите клавиши **CTRL+F5** , чтобы запустить страницу Default.aspx без отладки, или нажмите клавишу F5, чтобы запустить эту страницу с отладкой.</span><span class="sxs-lookup"><span data-stu-id="c45f3-105">Press **CTRL+F5** to run the Default.aspx page without debugging, or press F5 to run the page with debugging.</span></span>

     <span data-ttu-id="c45f3-106">В рамках процесса сборки происходит компиляция отчета, и все обнаруженные ошибки (такие как синтаксические ошибки в выражениях, используемых в отчете) добавляются к **списку задач** , находящемуся в нижней части окна Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c45f3-106">As part of the build process, the report is compiled and any errors found (such as a syntax error in an expression used in the report) are added to the **Task List** that is located at the bottom of the Visual Studio window.</span></span>

     <span data-ttu-id="c45f3-107">Веб-страница откроется в браузере.</span><span class="sxs-lookup"><span data-stu-id="c45f3-107">The webpage appears in the browser.</span></span> <span data-ttu-id="c45f3-108">В отчете отображается элемент управления ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="c45f3-108">The ReportViewer control displays the report.</span></span> <span data-ttu-id="c45f3-109">Для просмотра отчета, изменения масштаба и экспорта отчета в Excel можно использовать панель инструментов.</span><span class="sxs-lookup"><span data-stu-id="c45f3-109">You can use the toolbar to browse through the report, zoom, and export the report to Excel.</span></span>

2.  <span data-ttu-id="c45f3-110">Наведите курсор мыши на любую строку в столбце **Имя** .</span><span class="sxs-lookup"><span data-stu-id="c45f3-110">Hover the mouse over any of the rows under **Name** column.</span></span> <span data-ttu-id="c45f3-111">Курсор мыши примет форму руки.</span><span class="sxs-lookup"><span data-stu-id="c45f3-111">The mouse cursor will display a Hand symbol.</span></span>

3.  <span data-ttu-id="c45f3-112">Щелкните любое значение в столбце **Имя** .</span><span class="sxs-lookup"><span data-stu-id="c45f3-112">Click a value in the **Name** column.</span></span> <span data-ttu-id="c45f3-113">Будет показан дочерний отчет с соответствующими отфильтрованными данными.</span><span class="sxs-lookup"><span data-stu-id="c45f3-113">The child report is shown with the corresponding filtered data.</span></span>

4.  <span data-ttu-id="c45f3-114">Щелкните значок **Возврат к родительскому отчету**на панели инструментов **ReportViewer** , чтобы перейти к **родительскому** отчету.</span><span class="sxs-lookup"><span data-stu-id="c45f3-114">Click the icon, **Go back to parent report**, in the **ReportViewer** tool bar to navigate back to the **Parent** report.</span></span>

     <span data-ttu-id="c45f3-115">![Детализация служб SSRS с помощью ReportViewer](../../2014/tutorials/media/ssrs-drillthrough-report.png "Детализация служб SSRS с помощью ReportViewer")</span><span class="sxs-lookup"><span data-stu-id="c45f3-115">![ssrs drill through using ReportViewer](../../2014/tutorials/media/ssrs-drillthrough-report.png "ssrs drill through using ReportViewer")</span></span>

5.  <span data-ttu-id="c45f3-116">Закройте браузер, чтобы выйти из приложения.</span><span class="sxs-lookup"><span data-stu-id="c45f3-116">Close the browser to exit.</span></span>


