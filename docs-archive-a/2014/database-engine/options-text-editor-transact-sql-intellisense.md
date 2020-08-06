---
title: Параметры (текстовый редактор — Transact-SQL-IntelliSense) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.Advanced
- VS.ToolsOptionsPages.Text_Editor.SQL_Server_Tools.Advanced
dev_langs:
- TSQL
ms.assetid: 1855d916-5bf9-4d94-b0fb-9f9bb05ff950
author: rothja
ms.author: jroth
ms.openlocfilehash: 2d8f9c865516dc5e4c0ddadbdc908a9b4c8ec366
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666211"
---
# <a name="options-text-editor-transact-sql-intellisense"></a><span data-ttu-id="4f169-102">Параметры (текстовый редактор — Transact-SQL-IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="4f169-102">Options (Text Editor-Transact-SQL-IntelliSense)</span></span>
  <span data-ttu-id="4f169-103">Диалоговое окно **Параметры** позволяет изменять параметры технологии IntelliSense для редактора запросов [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f169-103">The **Options** dialog box lets you change the IntelliSense settings for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="4f169-104">Для доступа к этим параметрам в меню **Сервис** выберите пункт **Параметры**, разверните папку **Редактор текстов**, раскройте папку **Transact-SQL** и нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="4f169-104">These settings are available when, on the **Tools** menu, you click **Options**, expand the **Text Editor** folder, expand the **Transact-SQL** folder, and then click **Advanced**.</span></span>  
  
## <a name="transact-sql-intellisense-settings"></a><span data-ttu-id="4f169-105">Параметры технологии IntelliSense для Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f169-105">Transact-SQL IntelliSense Settings</span></span>  
 <span data-ttu-id="4f169-106">Указывает параметры технологии IntelliSense для редактора запросов [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f169-106">Specifies the IntelliSense options for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span>  
  
### <a name="enable-intellisense"></a><span data-ttu-id="4f169-107">Включение технологии IntelliSense</span><span class="sxs-lookup"><span data-stu-id="4f169-107">Enable IntelliSense</span></span>  
 <span data-ttu-id="4f169-108">Включает функции технологии IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4f169-108">Enables the IntelliSense features.</span></span> <span data-ttu-id="4f169-109">Если этот флажок не установлен, то определенные параметры технологии IntelliSense недоступны.</span><span class="sxs-lookup"><span data-stu-id="4f169-109">When this box is not selected, the specific IntelliSense options are unavailable.</span></span> <span data-ttu-id="4f169-110">По умолчанию этот флажок установлен.</span><span class="sxs-lookup"><span data-stu-id="4f169-110">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="4f169-111">**Подчеркивать ошибки**</span><span class="sxs-lookup"><span data-stu-id="4f169-111">**Underline errors**</span></span>  
 <span data-ttu-id="4f169-112">Обнаруживает синтаксические и семантические ошибки в инструкциях [!INCLUDE[tsql](../includes/tsql-md.md)] в окне запроса.</span><span class="sxs-lookup"><span data-stu-id="4f169-112">Identifies syntax and semantic errors in [!INCLUDE[tsql](../includes/tsql-md.md)] statements in the query window.</span></span> <span data-ttu-id="4f169-113">Все ошибки и предупреждения показаны красным цветом.</span><span class="sxs-lookup"><span data-stu-id="4f169-113">All errors and warnings appear in red.</span></span> <span data-ttu-id="4f169-114">Ошибки и предупреждения поддерживаются только для инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] , для которых реализована технология IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4f169-114">Errors and warnings are supported only for the [!INCLUDE[tsql](../includes/tsql-md.md)] statements for which IntelliSense has been implemented.</span></span> <span data-ttu-id="4f169-115">По умолчанию этот флажок установлен.</span><span class="sxs-lookup"><span data-stu-id="4f169-115">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="4f169-116">**Определить структуру инструкций**</span><span class="sxs-lookup"><span data-stu-id="4f169-116">**Outline statements**</span></span>  
 <span data-ttu-id="4f169-117">Включает функцию структурирования при открытии файла.</span><span class="sxs-lookup"><span data-stu-id="4f169-117">Enables the outlining feature when a file is opened.</span></span> <span data-ttu-id="4f169-118">В результате создаются свертываемые блоки кода [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f169-118">This creates collapsible blocks of [!INCLUDE[tsql](../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="4f169-119">По умолчанию этот флажок установлен.</span><span class="sxs-lookup"><span data-stu-id="4f169-119">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="4f169-120">**Максимальный размер скрипта**</span><span class="sxs-lookup"><span data-stu-id="4f169-120">**Maximum script size**</span></span>  
 <span data-ttu-id="4f169-121">Определяет размер, при котором отключается функциональность технологии IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4f169-121">Specifies the size at which IntelliSense functionality is disabled.</span></span> <span data-ttu-id="4f169-122">Если скрипт превышает указанный размер, выдается предупреждение.</span><span class="sxs-lookup"><span data-stu-id="4f169-122">If a script exceeds the specified size, a warning message is issued.</span></span> <span data-ttu-id="4f169-123">Все функции технологии IntelliSense, за исключением выделения цветом, отключаются для этого окна редактора.</span><span class="sxs-lookup"><span data-stu-id="4f169-123">All IntelliSense features, except color coding, are disabled for that editor window.</span></span> <span data-ttu-id="4f169-124">Технология IntelliSense повторно активируется, если удалить достаточный фрагмент текста, чтобы уменьшить размер скрипта до допустимого.</span><span class="sxs-lookup"><span data-stu-id="4f169-124">IntelliSense is reenabled when enough text is deleted to reduce the script size to under the limit.</span></span> <span data-ttu-id="4f169-125">Включение технологии IntelliSense для крупных скриптов может привести к снижению производительности медленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="4f169-125">Enabling IntelliSense for large script sizes can decrease performance on slow computers.</span></span> <span data-ttu-id="4f169-126">Допустимые размеры 100 КБ, 500 КБ, 1 МБ, 2 МБ и неограниченный.</span><span class="sxs-lookup"><span data-stu-id="4f169-126">The allowed sizes are 100 KB, 500 KB, 1 MB, 2 MB, and Unlimited.</span></span> <span data-ttu-id="4f169-127">По умолчанию установлено значение 1 МБ.</span><span class="sxs-lookup"><span data-stu-id="4f169-127">The default is 1 MB.</span></span>  
  
 <span data-ttu-id="4f169-128">**Регистр для имен встроенных функций**</span><span class="sxs-lookup"><span data-stu-id="4f169-128">**Casing for built-in function names**</span></span>  
 <span data-ttu-id="4f169-129">Указывает, используются ли в именах встроенных функций [!INCLUDE[tsql](../includes/tsql-md.md)], которые включены в список завершения, прописные буквы (например, DATEADD) или строчные буквы (например, dateadd).</span><span class="sxs-lookup"><span data-stu-id="4f169-129">Specifies whether the names of built-in [!INCLUDE[tsql](../includes/tsql-md.md)] functions that are included in completion lists use uppercase letters, such as DATEADD; or lowercase letters, such as dateadd.</span></span> <span data-ttu-id="4f169-130">Выберите параметр, который в наибольшей степени согласуется с используемыми соглашениями по разработке кода [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f169-130">Select the option that best matches the [!INCLUDE[tsql](../includes/tsql-md.md)] coding conventions that you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f169-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f169-131">See Also</span></span>  
 [<span data-ttu-id="4f169-132">Устранение неполадок IntelliSense &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4f169-132">Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;</span></span>](../relational-databases/scripting/troubleshooting-intellisense.md)  
  
  
