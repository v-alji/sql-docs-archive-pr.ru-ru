---
title: Устранение неполадок в работе IntelliSense
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- unavailable options [IntelliSense]
- IntelliSense [SQL Server], troubleshooting
- IntelliSense [SQL Server], unavailable options
- troubleshooting [IntelliSense]
ms.assetid: 4b72ffc6-aea2-4e11-ab36-fa2de4d7bcc5
author: rothja
ms.author: jroth
ms.openlocfilehash: 087baf616fc215c480ae78621623cbe1ed512b57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733810"
---
# <a name="troubleshooting-intellisense-sql-server-management-studio"></a><span data-ttu-id="7da8c-102">Устранение сбоев в работе IntelliSense (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7da8c-102">Troubleshooting IntelliSense (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7da8c-103">В некоторых случаях параметры технологии IntelliSense могут работать не так, как ожидается.</span><span class="sxs-lookup"><span data-stu-id="7da8c-103">There are certain cases when the IntelliSense options might not work as you expect.</span></span>  
  
## <a name="conditions-that-affect-intellisense"></a><span data-ttu-id="7da8c-104">Условия, влияющие на работу технологии IntelliSense</span><span class="sxs-lookup"><span data-stu-id="7da8c-104">Conditions That Affect IntelliSense</span></span>  
 <span data-ttu-id="7da8c-105">Следующие условия могут повлиять на работу технологии IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="7da8c-105">The following conditions might affect the behavior of IntelliSense:</span></span>  
  
-   <span data-ttu-id="7da8c-106">Выше позиции курсора есть ошибка кода.</span><span class="sxs-lookup"><span data-stu-id="7da8c-106">There is a code error above the cursor.</span></span>  
  
     <span data-ttu-id="7da8c-107">Если в коде выше текущей позиции ввода имеется незавершенная инструкция или другая ошибка, то технология IntelliSense может оказаться не в состоянии проанализировать элементы кода и поэтому работать не будет.</span><span class="sxs-lookup"><span data-stu-id="7da8c-107">If there is an incomplete statement or other coding error above the location of the insertion point, IntelliSense may be unable to parse the code elements, and therefore will not work.</span></span> <span data-ttu-id="7da8c-108">Чтобы снова включить технологию IntelliSense, можно заключить соответствующий код в комментарий.</span><span class="sxs-lookup"><span data-stu-id="7da8c-108">You can comment out the applicable code to enable IntelliSense again.</span></span>  
  
-   <span data-ttu-id="7da8c-109">Позиция ввода находится внутри комментария.</span><span class="sxs-lookup"><span data-stu-id="7da8c-109">The insertion point is inside a code comment.</span></span>  
  
     <span data-ttu-id="7da8c-110">Параметры технологии IntelliSense недоступны в том случае, если позиция ввода находится в исходном файле внутри комментария.</span><span class="sxs-lookup"><span data-stu-id="7da8c-110">IntelliSense options are not available when the insertion point is within a comment in your source file.</span></span>  
  
-   <span data-ttu-id="7da8c-111">Позиция ввода находится внутри строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="7da8c-111">The insertion point is inside a string literal.</span></span>  
  
     <span data-ttu-id="7da8c-112">Параметры технологии IntelliSense недоступны в том случае, если позиция ввода находится внутри кавычек, содержащих строковый литерал, например:</span><span class="sxs-lookup"><span data-stu-id="7da8c-112">IntelliSense options are not available when the insertion point is inside the quotation marks around a string literal, for example:</span></span>  
  
     `WHERE FirstName LIKE 'Patri%|'`  
  
-   <span data-ttu-id="7da8c-113">Функции автоматизации отключены.</span><span class="sxs-lookup"><span data-stu-id="7da8c-113">The automatic options are turned off.</span></span>  
  
     <span data-ttu-id="7da8c-114">Многие функции технологии IntelliSense работают автоматически по умолчанию, но любую из них можно отключить.</span><span class="sxs-lookup"><span data-stu-id="7da8c-114">Many IntelliSense features work automatically by default, but you can disable any feature.</span></span>  
  
     <span data-ttu-id="7da8c-115">Даже если автоматическое завершение инструкций отключено, то использование функции технологии IntelliSense возможно.</span><span class="sxs-lookup"><span data-stu-id="7da8c-115">Even when automatic statement completion is disabled, you can use an IntelliSense feature.</span></span> <span data-ttu-id="7da8c-116">Дополнительные сведения см. в статье [Настройка IntelliSense (среда SQL Server Management Studio)](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="7da8c-116">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
## <a name="database-engine-query-intellisense"></a><span data-ttu-id="7da8c-117">Поддержка технологии IntelliSense в редакторе запросов к ядру СУБД</span><span class="sxs-lookup"><span data-stu-id="7da8c-117">Database Engine Query IntelliSense</span></span>  
 <span data-ttu-id="7da8c-118">В отношении редактора запросов [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="7da8c-118">The following issues apply to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor:</span></span>  
  
-   <span data-ttu-id="7da8c-119">Функция IntelliSense в редакторе запросов [!INCLUDE[ssDE](../../includes/ssde-md.md)] поддерживает не все элементы синтаксиса языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7da8c-119">The IntelliSense functionality of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="7da8c-120">Справка по параметрам не предоставляется по параметрам некоторых объектов, например расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="7da8c-120">Parameter help does not support the parameters in some objects, such as extended stored procedures.</span></span> <span data-ttu-id="7da8c-121">Дополнительные сведения см. в разделе [Синтаксис языка Transact-SQL, поддерживаемый технологией IntelliSense](transact-sql-syntax-supported-by-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="7da8c-121">For more information, see [Transact-SQL Syntax Supported by IntelliSense](transact-sql-syntax-supported-by-intellisense.md).</span></span>  
  
-   <span data-ttu-id="7da8c-122">Технология Intellisense доступна только в случае, если редактор запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] подключен к экземпляру [!INCLUDE[ssDE](../../includes/ssde-md.md)] версии [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="7da8c-122">IntelliSense is only available when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor is connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="7da8c-123">Технология Intellisense не доступна, когда редактор запросов подключен к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="7da8c-123">IntelliSense is not available when the Query Editor is connected to earlier versions of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="7da8c-124">Поддержка технологии IntelliSense отключается в редакторе запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] при включении режима SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="7da8c-124">IntelliSense is turned off in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor when the SQLCMD mode is set on.</span></span>  
  
-   <span data-ttu-id="7da8c-125">Функциональность технологии IntelliSense не охватывает объекты базы данных, созданные в другом соединении, установленном после подключения окна редактора к базе данных.</span><span class="sxs-lookup"><span data-stu-id="7da8c-125">IntelliSense functionality does not cover database objects created by another connection after your editor window connected to the database.</span></span> <span data-ttu-id="7da8c-126">Если в функциях технологии IntelliSense отсутствуют такие объекты, как списки завершения, можно выбрать один из трех механизмов обновления кэша объектов для окна редактора.</span><span class="sxs-lookup"><span data-stu-id="7da8c-126">If objects are missing from IntelliSense features such as completion lists, you can choose one of these three mechanisms to refresh the cache of objects for your editor window:</span></span>  
  
    -   <span data-ttu-id="7da8c-127">В меню **Правка** выберите пункт **IntelliSense**, а затем пункт **Обновить локальный кэш**.</span><span class="sxs-lookup"><span data-stu-id="7da8c-127">Select the **Edit** menu, select **IntelliSense**, then select **Refresh Local Cache**.</span></span>  
  
    -   <span data-ttu-id="7da8c-128">Используйте сочетание клавиш CTRL+SHIFT+R.</span><span class="sxs-lookup"><span data-stu-id="7da8c-128">Use the CTRL+Shift+R keyboard shortcut.</span></span>  
  
    -   <span data-ttu-id="7da8c-129">Отключите окно редактора от экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и установите соединение повторно.</span><span class="sxs-lookup"><span data-stu-id="7da8c-129">Disconnect your editor window from the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and reconnect.</span></span>  
  
-   <span data-ttu-id="7da8c-130">В списки завершения не включаются объекты базы данных, на которые нет разрешений.</span><span class="sxs-lookup"><span data-stu-id="7da8c-130">Completion lists do not include database objects for which you do not have permissions.</span></span> <span data-ttu-id="7da8c-131">Ссылки на объекты, для которых есть разрешения, в технологии IntelliSense отмечаются флагами.</span><span class="sxs-lookup"><span data-stu-id="7da8c-131">IntelliSense flags references to objects for which you do have permissions.</span></span> <span data-ttu-id="7da8c-132">Например, если открыть скрипт, написанный другим пользователем, все ссылки на объекты, для которых у другого пользователя есть разрешения, а у вас нет, отмечаются флагами как неверные.</span><span class="sxs-lookup"><span data-stu-id="7da8c-132">For example, if you open a script that is written by someone else, any references to objects for which that person has permissions and you do not are flagged as incorrect.</span></span>  
  
-   <span data-ttu-id="7da8c-133">Списки завершения могут перестать функционировать при разрыве соединения с экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7da8c-133">Completion lists might stop working if you lose the connection to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="7da8c-134">В этом случае необходимо восстановить соединение с экземпляром.</span><span class="sxs-lookup"><span data-stu-id="7da8c-134">Reconnect to the instance.</span></span>  
  
  
