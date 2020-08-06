---
title: Отмена запрета предупреждений для пользовательских отчетов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 0deed900-c910-4d12-aac0-6ab9e39eb068
author: stevestein
ms.author: sstein
ms.openlocfilehash: 725362ff7f8a6c282529f652e8813a8083257eb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727857"
---
# <a name="unsuppress-run-custom-report-warnings"></a><span data-ttu-id="638f0-102">Отмена подавления предупреждений для пользовательских отчетов</span><span class="sxs-lookup"><span data-stu-id="638f0-102">Unsuppress Run Custom Report Warnings</span></span>
  <span data-ttu-id="638f0-103">Для пользовательских отчетов предусмотрено два типа предупреждающих диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="638f0-103">There are two warning dialog boxes for custom reports.</span></span> <span data-ttu-id="638f0-104">В этом разделе описано, как отменить подавление отображения этих полей в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="638f0-104">This topic describes how to unsuppress the display of these boxes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="638f0-105">По умолчанию перед запуском пользовательского отчета отображается диалоговое окно **Запустить пользовательский отчет** .</span><span class="sxs-lookup"><span data-stu-id="638f0-105">By default, the **Run Custom Reports** dialog box appears before a custom report runs.</span></span> <span data-ttu-id="638f0-106">Если установить флажок **Больше не показывать это предупреждение** , то это диалоговое окно больше отображаться не будет.</span><span class="sxs-lookup"><span data-stu-id="638f0-106">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span> <span data-ttu-id="638f0-107">Также по умолчанию диалоговое окно **Запустить пользовательский отчет** отображается, если после открытия одного пользовательского отчета нажать ссылку для открытия другого отчета.</span><span class="sxs-lookup"><span data-stu-id="638f0-107">Also by default, the **Run Custom Reports** dialog box appears when you open a custom report and then click a link to open another custom report.</span></span> <span data-ttu-id="638f0-108">В этом диалоговом окне отображается полный путь к файлу пользовательского детализированного отчета.</span><span class="sxs-lookup"><span data-stu-id="638f0-108">This dialog box displays the fill path to the drill-through custom report file.</span></span> <span data-ttu-id="638f0-109">Если установить флажок **Больше не показывать это предупреждение** , то это диалоговое окно больше отображаться не будет.</span><span class="sxs-lookup"><span data-stu-id="638f0-109">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="638f0-110">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="638f0-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-unsuppress-the-main-custom-report-warning-dialog-box"></a><span data-ttu-id="638f0-111">Отмена подавления основного диалогового окна предупреждения для пользовательских отчетов</span><span class="sxs-lookup"><span data-stu-id="638f0-111">To unsuppress the main custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="638f0-112">Подключитесь к \<*Server*> \\ < *общей папке* >| \<*Drive*> \Documents and Settings \\<UserProfile \> \Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span><span class="sxs-lookup"><span data-stu-id="638f0-112">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="638f0-113">Щелкните правой кнопкой мыши `reports.xml` и выберите пункт **изменить**.</span><span class="sxs-lookup"><span data-stu-id="638f0-113">Right-click `reports.xml`, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="638f0-114">Измените\*\* \<SuppressWarning> значение \</SuppressWarning> true \<SuppressWarning> на \</SuppressWarning> false\*\*.</span><span class="sxs-lookup"><span data-stu-id="638f0-114">Change**\<SuppressWarning>true\</SuppressWarning> to \<SuppressWarning>false\</SuppressWarning>**.</span></span>  
  
4.  <span data-ttu-id="638f0-115">Перезапустите [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="638f0-115">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-unsuppress-the-drill-through-custom-report-warning-dialog-box"></a><span data-ttu-id="638f0-116">Отмена подавления диалогового окна предупреждений для детализированных пользовательских отчетов</span><span class="sxs-lookup"><span data-stu-id="638f0-116">To unsuppress the drill-through custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="638f0-117">Подключитесь к \<*Server*> \\ < *общей папке* >| \<*Drive*> \Documents and Settings \\<UserProfile \> \Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span><span class="sxs-lookup"><span data-stu-id="638f0-117">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="638f0-118">Щелкните правой кнопкой мыши `reports.xml` и выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="638f0-118">Right-click `reports.xml`, and click **Edit**.</span></span>  
  
3.  <span data-ttu-id="638f0-119">Измените \*\* \<SuppressDrillthroughWarning> значение \</SuppressDrillthroughWarning> true \<SuppressDrillthroughWarning> на \</SuppressDrillthroughWarning> false\*\*.</span><span class="sxs-lookup"><span data-stu-id="638f0-119">Change **\<SuppressDrillthroughWarning>true\</SuppressDrillthroughWarning>to \<SuppressDrillthroughWarning>false\</SuppressDrillthroughWarning>**.</span></span>  
  
4.  <span data-ttu-id="638f0-120">Перезапустите [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="638f0-120">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="638f0-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="638f0-121">See Also</span></span>  
 <span data-ttu-id="638f0-122">[Пользовательские отчеты в Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="638f0-122">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="638f0-123">[Добавление пользовательского отчета в Management Studio](add-a-custom-report-to-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="638f0-123">[Add a Custom Report to Management Studio](add-a-custom-report-to-management-studio.md) </span></span>  
 [<span data-ttu-id="638f0-124">Использование пользовательских отчетов для свойств узлов обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="638f0-124">Use Custom Reports with Object Explorer Node Properties</span></span>](use-custom-reports-with-object-explorer-node-properties.md)  
  
  
