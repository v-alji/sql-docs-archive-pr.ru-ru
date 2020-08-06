---
title: Запуск и остановка набора элементов сбора | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection sets [SQL Server], stopping
- collection sets [SQL Server], starting
ms.assetid: 48a7b2fe-6bc3-4278-a7ec-1babc1290345
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e37d4b2edcd7a6e048c405b072bcbf9b1fef78c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667239"
---
# <a name="start-or-stop-a-collection-set"></a><span data-ttu-id="238bc-102">Запуск или остановка набора элементов сбора</span><span class="sxs-lookup"><span data-stu-id="238bc-102">Start or Stop a Collection Set</span></span>
  <span data-ttu-id="238bc-103">В этом разделе описывается запуск и остановка набора элементов сбора в среде [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="238bc-103">This topic describes how to start or stop a collection set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="238bc-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="238bc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="238bc-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="238bc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="238bc-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="238bc-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="238bc-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="238bc-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="238bc-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="238bc-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="238bc-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="238bc-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="238bc-110">**Запуск и остановка набора элементов сбора с помощью:**</span><span class="sxs-lookup"><span data-stu-id="238bc-110">**To start or stop a collection set, using:**</span></span>  
  
     [<span data-ttu-id="238bc-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="238bc-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="238bc-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="238bc-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="238bc-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="238bc-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="238bc-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="238bc-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="238bc-115">Хранимые процедуры и представления каталога сборщика данных хранятся в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="238bc-115">Data Collector stored procedures and catalog views are stored in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="238bc-116">В отличие от обычных хранимых процедур, параметры хранимых процедур для сборщика данных жестко типизированы и не поддерживают автоматическое преобразование типов данных.</span><span class="sxs-lookup"><span data-stu-id="238bc-116">Unlike regular stored procedures, the parameters for data collector stored procedures are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="238bc-117">Если эти параметры не вызываются вместе с правильными типами данных входных параметров, как указано в описании аргумента, хранимая процедура возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="238bc-117">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="238bc-118">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="238bc-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="238bc-119">Должен быть запущен агент SQL Server.</span><span class="sxs-lookup"><span data-stu-id="238bc-119">SQL Server Agent must be started.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="238bc-120">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="238bc-120">Recommendations</span></span>  
  
-   <span data-ttu-id="238bc-121">Для получения информации о наборах элементов сбора запросите представление каталога [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="238bc-121">To obtain information about collection sets, query the [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) catalog view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="238bc-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="238bc-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="238bc-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="238bc-123">Permissions</span></span>  
 <span data-ttu-id="238bc-124">Требуется членство в предопределенной роли базы данных **dc_operator** .</span><span class="sxs-lookup"><span data-stu-id="238bc-124">Requires membership in the **dc_operator** fixed database role.</span></span> <span data-ttu-id="238bc-125">Если набор элементов сбора не имеет учетной записи-посредника, требуется членство в предопределенной роли сервера **sysadmin** . Примеры</span><span class="sxs-lookup"><span data-stu-id="238bc-125">If the collection set does not have a proxy account, membership in the **sysadmin** fixed server role is required.Examples</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="238bc-126">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="238bc-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="238bc-127">Запуск набора сбора</span><span class="sxs-lookup"><span data-stu-id="238bc-127">To start a collection set</span></span>  
  
1.  <span data-ttu-id="238bc-128">В обозревателе объектов разверните узел **Управление** , затем узел **Сбор данных**и узел **Наборы элементов сбора системных данных**.</span><span class="sxs-lookup"><span data-stu-id="238bc-128">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="238bc-129">Щелкните правой кнопкой мыши необходимый для запуска набор сбора и выберите команду **Запустить набор сбора данных**.</span><span class="sxs-lookup"><span data-stu-id="238bc-129">Right-click the collection set that you want to start, and then click **Start Data Collection Set**.</span></span>  
  
     <span data-ttu-id="238bc-130">Результат этого действия выводится в окне, а зеленая стрелка на значке набора сбора означает его запуск.</span><span class="sxs-lookup"><span data-stu-id="238bc-130">A message box displays the results of this action, and a green arrow on the icon for the collection set indicates that the collection set has started.</span></span>  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="238bc-131">Остановка набора элементов сбора:</span><span class="sxs-lookup"><span data-stu-id="238bc-131">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="238bc-132">В обозревателе объектов разверните узел **Управление** , затем узел **Сбор данных**и узел **Наборы элементов сбора системных данных**.</span><span class="sxs-lookup"><span data-stu-id="238bc-132">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="238bc-133">Щелкните правой кнопкой мыши набор элементов сбора, который необходимо остановить, и выберите команду **Остановить набор сбора данных**.</span><span class="sxs-lookup"><span data-stu-id="238bc-133">Right-click the collection set that you want to stop, and then click **Stop Data Collection Set**.</span></span>  
  
     <span data-ttu-id="238bc-134">Результат этого действия выводится в окне, а красный круг на значке набора сбора означает его остановку.</span><span class="sxs-lookup"><span data-stu-id="238bc-134">A message box displays the results of this action, and a red circle on the icon for the collection set indicates that the collection set has stopped.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="238bc-135">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="238bc-135">Using Transact-SQL</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="238bc-136">Запуск набора сбора</span><span class="sxs-lookup"><span data-stu-id="238bc-136">To start a collection set</span></span>  
  
1.  <span data-ttu-id="238bc-137">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="238bc-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="238bc-138">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="238bc-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="238bc-139">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="238bc-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="238bc-140">В этом примере используется процедура [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) для запуска набора элементов сбора с идентификатором `1`.</span><span class="sxs-lookup"><span data-stu-id="238bc-140">This example uses [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) to start the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_start_collection_set @collection_set_id = 1;  
```  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="238bc-141">Остановка набора элементов сбора:</span><span class="sxs-lookup"><span data-stu-id="238bc-141">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="238bc-142">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="238bc-142">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="238bc-143">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="238bc-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="238bc-144">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="238bc-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="238bc-145">В этом примере используется процедура [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) для остановки набора элементов сбора с идентификатором `1`.</span><span class="sxs-lookup"><span data-stu-id="238bc-145">This example uses [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) to stop the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_stop_collection_set @collection_set_id = 1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="238bc-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="238bc-146">See Also</span></span>  
 <span data-ttu-id="238bc-147">[Представления сборщика данных (Transact-SQL)](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="238bc-147">[Data Collector Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span></span>  
 [<span data-ttu-id="238bc-148">Сбор данных</span><span class="sxs-lookup"><span data-stu-id="238bc-148">Data Collection</span></span>](data-collection.md)  
  
  
