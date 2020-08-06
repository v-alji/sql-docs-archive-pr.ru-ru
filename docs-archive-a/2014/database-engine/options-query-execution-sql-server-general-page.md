---
title: Параметры (выполнение запроса-SQL Server-страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryExecution.SqlServer.SqlExecutionGeneral
ms.assetid: 3f8d59bc-3f97-4e5d-8b86-5ac670d20780
author: rothja
ms.author: jroth
ms.openlocfilehash: eaa95293636d02674fb720dcd1b8146279f78e72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667861"
---
# <a name="options-query-execution-sql-server-general-page"></a><span data-ttu-id="74385-102">Параметры (выполнение запроса-SQL Server-страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="74385-102">Options (Query Execution-SQL Server-General Page)</span></span>
  <span data-ttu-id="74385-103">Используйте эту страницу, чтобы задать параметры для запросов служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="74385-103">Use this page to specify the options for running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="74385-104">Изменения этих параметров применяются только к новым запросам [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="74385-104">Changes to these options are only applied to new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="74385-105">Для изменения параметров текущего запроса выберите пункт **Параметры запроса** в меню **Запрос** или щелкните правой кнопкой мыши в окне запроса [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и выберите пункт **Параметры запроса**.</span><span class="sxs-lookup"><span data-stu-id="74385-105">To change the options for a current query, click **Query Options** on the **Query** menu, or in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window right-click and select **Query Options**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="74385-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="74385-106">Options</span></span>  
 <span data-ttu-id="74385-107">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="74385-107">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="74385-108">Значение по умолчанию, равное 0, указывает на то, что [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] будет продолжать ожидание результатов, пока все из них не будут получены.</span><span class="sxs-lookup"><span data-stu-id="74385-108">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="74385-109">При установке значения больше 0 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] прервет запрос после получения указанного числа строк.</span><span class="sxs-lookup"><span data-stu-id="74385-109">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="74385-110">Для выключения этого параметра (чтобы возвращались все строки) задайте SET ROWCOUNT 0.</span><span class="sxs-lookup"><span data-stu-id="74385-110">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="74385-111">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="74385-111">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="74385-112">Значение по умолчанию, равное 2 147 483 647 байт, указывает, что [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] предоставит полный набор данных до ограничения в полях данных `text` и `ntext`.</span><span class="sxs-lookup"><span data-stu-id="74385-112">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide complete data fields up to the limit of `text` and `ntext` data fields.</span></span> <span data-ttu-id="74385-113">Задав меньшее число, можно ограничить вывод результатов в случае больших значений.</span><span class="sxs-lookup"><span data-stu-id="74385-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="74385-114">Содержимое столбцов большего размера, чем заданное число, будет усекаться.</span><span class="sxs-lookup"><span data-stu-id="74385-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="74385-115">**Время ожидания выполнения**</span><span class="sxs-lookup"><span data-stu-id="74385-115">**Execution time-out**</span></span>  
 <span data-ttu-id="74385-116">Задает значение по умолчанию в диалоговом окне **Создание соединения** .</span><span class="sxs-lookup"><span data-stu-id="74385-116">Sets the default value in the **New Connection** dialog box.</span></span> <span data-ttu-id="74385-117">Используйте это поле, чтобы указать [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] количество секунд ожидания перед отменой запроса.</span><span class="sxs-lookup"><span data-stu-id="74385-117">Use this spin box to tell [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="74385-118">Значение 0 указывает на бесконечное ожидание или отсутствие времени ожидания. Это значение равно 0 в новой установке.</span><span class="sxs-lookup"><span data-stu-id="74385-118">A value of 0 indicates an infinite wait, or no time-out. This value is 0 on a new installation.</span></span>  
  
 <span data-ttu-id="74385-119">**Разделитель пакетов**</span><span class="sxs-lookup"><span data-stu-id="74385-119">**Batch separator**</span></span>  
 <span data-ttu-id="74385-120">Введите слово, которое будет использоваться для разделения инструкций языка [!INCLUDE[tsql](../includes/tsql-md.md)] на пакеты.</span><span class="sxs-lookup"><span data-stu-id="74385-120">Type a word that you use to separate [!INCLUDE[tsql](../includes/tsql-md.md)] statements into batches.</span></span> <span data-ttu-id="74385-121">Значение по умолчанию — GO.</span><span class="sxs-lookup"><span data-stu-id="74385-121">The default is GO.</span></span>  
  
 <span data-ttu-id="74385-122">**По умолчанию открывать новые запросы в режиме SQLCMD**</span><span class="sxs-lookup"><span data-stu-id="74385-122">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="74385-123">При установке этого флажка новые запросы будут открываться в режиме SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="74385-123">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="74385-124">Дополнительные сведения о режиме SQLCMD см. в разделе [Изменение скриптов SQLCMD при помощи редактора запросов](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="74385-124">For more information about SQLCMD mode, see [Edit SQLCMD Scripts with Query Editor](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span>  
  
 <span data-ttu-id="74385-125">При выборе этого параметра следует учитывать следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="74385-125">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="74385-126">Технология IntelliSense в редакторе запросов компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] отключена.</span><span class="sxs-lookup"><span data-stu-id="74385-126">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="74385-127">Поскольку редактор запросов не запускается из командной строки, невозможно передать ему такие параметры командной строки, как переменные.</span><span class="sxs-lookup"><span data-stu-id="74385-127">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="74385-128">Поскольку редактор запросов не может ответить на подсказки и приглашения операционной системы, будьте внимательны и не запускайте интерактивные инструкции.</span><span class="sxs-lookup"><span data-stu-id="74385-128">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="74385-129">**По умолчанию**</span><span class="sxs-lookup"><span data-stu-id="74385-129">**Reset to Default**</span></span>  
 <span data-ttu-id="74385-130">Выберите этот пункт для сброса всех значений этой страницы и установки значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="74385-130">Click to reset all values on this page to the original default values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74385-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="74385-131">See Also</span></span>  
 [<span data-ttu-id="74385-132">Программа sqlcmd</span><span class="sxs-lookup"><span data-stu-id="74385-132">sqlcmd Utility</span></span>](../tools/sqlcmd-utility.md)  
  
  
