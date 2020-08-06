---
title: Создание синонимов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
f1_keywords:
- sql12.swb.synonym.general.f1
helpviewer_keywords:
- creating synonyms
- synonyms [SQL Server], creating
ms.assetid: fedfa7a5-d0b6-4e2b-90f4-a08122958e33
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3dc18c9d0d6048c4190ba56725dd332f2dfb629e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654116"
---
# <a name="create-synonyms"></a><span data-ttu-id="823d5-102">Создание синонимов</span><span class="sxs-lookup"><span data-stu-id="823d5-102">Create Synonyms</span></span>
  <span data-ttu-id="823d5-103">В этом разделе описывается создание синонима в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="823d5-103">This topic describes how to create a synonym in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="823d5-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="823d5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="823d5-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="823d5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="823d5-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="823d5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="823d5-107">**Создание синонима при помощи:**</span><span class="sxs-lookup"><span data-stu-id="823d5-107">**To create a synonym, using:**</span></span>  
  
     [<span data-ttu-id="823d5-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="823d5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="823d5-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="823d5-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="823d5-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="823d5-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="823d5-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="823d5-111">Security</span></span>  
 <span data-ttu-id="823d5-112">Для создания синонима в заданной схеме пользователь должен иметь разрешение CREATE SYNONYM и, либо владеть схемой, либо иметь разрешение ALTER SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="823d5-112">To create a synonym in a given schema, a user must have CREATE SYNONYM permission and either own the schema or have ALTER SCHEMA permission.</span></span> <span data-ttu-id="823d5-113">Разрешение на выполнение CREATE SYNONYM можно предоставлять.</span><span class="sxs-lookup"><span data-stu-id="823d5-113">The CREATE SYNONYM permission is a grantable permission.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="823d5-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="823d5-114">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="823d5-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="823d5-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="823d5-116">Создание синонима</span><span class="sxs-lookup"><span data-stu-id="823d5-116">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="823d5-117">В **обозревателе объектов**разверните базу данных, в которой необходимо создать новое представление.</span><span class="sxs-lookup"><span data-stu-id="823d5-117">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="823d5-118">Щелкните правой кнопкой мыши папку **Синонимы** и выберите **Создать синоним...**</span><span class="sxs-lookup"><span data-stu-id="823d5-118">Right-click the **Synonyms** folder, then click **New Synonym...**.</span></span>  
  
3.  <span data-ttu-id="823d5-119">В диалоговом окне **Добавление синонима** введите следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="823d5-119">In the **Add Synonym** dialog box, enter the following information.</span></span>  
  
     <span data-ttu-id="823d5-120">**Имя синонима**</span><span class="sxs-lookup"><span data-stu-id="823d5-120">**Synonym name**</span></span>  
     <span data-ttu-id="823d5-121">Введите новое имя, которое будет использоваться для обращения к этому объекту.</span><span class="sxs-lookup"><span data-stu-id="823d5-121">Type the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="823d5-122">**Схема синонима**</span><span class="sxs-lookup"><span data-stu-id="823d5-122">**Synonym schema**</span></span>  
     <span data-ttu-id="823d5-123">Введите схему нового имени, которая будет использоваться для обращения к этому объекту.</span><span class="sxs-lookup"><span data-stu-id="823d5-123">Type the schema of the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="823d5-124">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="823d5-124">**Server name**</span></span>  
     <span data-ttu-id="823d5-125">Введите экземпляр сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="823d5-125">Type the server instance to connect to.</span></span>  
  
     <span data-ttu-id="823d5-126">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="823d5-126">**Database name**</span></span>  
     <span data-ttu-id="823d5-127">Введите или выберите базу данных, содержащую объект.</span><span class="sxs-lookup"><span data-stu-id="823d5-127">Type or select the database containing the object.</span></span>  
  
     <span data-ttu-id="823d5-128">**Схема**</span><span class="sxs-lookup"><span data-stu-id="823d5-128">**Schema**</span></span>  
     <span data-ttu-id="823d5-129">Введите или выберите схему, владеющую объектом.</span><span class="sxs-lookup"><span data-stu-id="823d5-129">Type or select the schema that owns the object.</span></span>  
  
     <span data-ttu-id="823d5-130">**Тип объекта**</span><span class="sxs-lookup"><span data-stu-id="823d5-130">**Object type**</span></span>  
     <span data-ttu-id="823d5-131">Выберите тип объекта.</span><span class="sxs-lookup"><span data-stu-id="823d5-131">Select the type of object.</span></span>  
  
     <span data-ttu-id="823d5-132">**Имя объекта**</span><span class="sxs-lookup"><span data-stu-id="823d5-132">**Object name**</span></span>  
     <span data-ttu-id="823d5-133">Введите имя объекта, которому должен соответствовать синоним.</span><span class="sxs-lookup"><span data-stu-id="823d5-133">Type the name of the object to which the synonym refers.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="823d5-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="823d5-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="823d5-135">Создание синонима</span><span class="sxs-lookup"><span data-stu-id="823d5-135">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="823d5-136">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="823d5-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="823d5-137">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="823d5-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="823d5-138">Скопируйте следующие примеры в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="823d5-138">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="823d5-139">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="823d5-139">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="823d5-140">В следующем примере создается синоним для существующей таблицы в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="823d5-140">The following example creates a synonym for an existing table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="823d5-141">Затем синоним используется в последующих примерах.</span><span class="sxs-lookup"><span data-stu-id="823d5-141">The synonym is then used in subsequent examples.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyAddressType  
FOR AdventureWorks2012.Person.AddressType;  
GO  
```  
  
 <span data-ttu-id="823d5-142">Следующий пример вставляет строку в базовую таблицу, на которую ссылается синоним `MyAddressType` .</span><span class="sxs-lookup"><span data-stu-id="823d5-142">The following example inserts a row into the base table that is referenced by the `MyAddressType` synonym.</span></span>  
  
```  
USE tempdb;  
GO  
INSERT INTO MyAddressType (Name)  
VALUES ('Test');  
GO  
```  
  
 <span data-ttu-id="823d5-143">Следующий пример демонстрирует, как на синоним можно сослаться в динамическом SQL.</span><span class="sxs-lookup"><span data-stu-id="823d5-143">The following example demonstrates how a synonym can be referenced in dynamic SQL.</span></span>  
  
```  
USE tempdb;  
GO  
EXECUTE ('SELECT Name FROM MyAddressType');  
GO  
```  
  
  
