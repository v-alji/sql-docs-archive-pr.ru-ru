---
title: Создание главного ключа базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2019
ms.prod: sql-server-2014
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], creating
ms.assetid: 8cb24263-e97d-4e4d-9429-6cf494a4d5eb
author: jaszymas
ms.author: jaszymas
ms.reviewer: carlrab
ms.openlocfilehash: cb8305d9d5a3c72e6dffafd231f21110a5abdd14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750615"
---
# <a name="create-a-database-master-key"></a><span data-ttu-id="a85f8-102">Создание главного ключа базы данных</span><span class="sxs-lookup"><span data-stu-id="a85f8-102">Create a Database Master Key</span></span>

<span data-ttu-id="a85f8-103">В этом разделе описывается создание главного ключа базы данных в `master` базе данных в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a85f8-103">This topic describes how to create a database master key in the `master` database in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>

<span data-ttu-id="a85f8-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="a85f8-104">**In This Topic**</span></span>

- <span data-ttu-id="a85f8-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a85f8-105">**Before you begin:**</span></span>

  [<span data-ttu-id="a85f8-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a85f8-106">Security</span></span>](#Security)

- [<span data-ttu-id="a85f8-107">Создание главного ключа базы данных с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a85f8-107">To create a database master key using Transact-SQL</span></span>](#TsqlProcedure)

## <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a85f8-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a85f8-108">Before You Begin</span></span>

### <a name="security"></a><a name="Security"></a> <span data-ttu-id="a85f8-109">безопасность</span><span class="sxs-lookup"><span data-stu-id="a85f8-109">Security</span></span>

#### <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a85f8-110">Permissions</span><span class="sxs-lookup"><span data-stu-id="a85f8-110">Permissions</span></span>

<span data-ttu-id="a85f8-111">Требует разрешения CONTROL для базы данных.</span><span class="sxs-lookup"><span data-stu-id="a85f8-111">Requires CONTROL permission on the database.</span></span>

## <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a85f8-112">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a85f8-112">Using Transact-SQL</span></span>

### <a name="to-create-a-database-master-key"></a><span data-ttu-id="a85f8-113">Создание главного ключа базы данных</span><span class="sxs-lookup"><span data-stu-id="a85f8-113">To create a database master key</span></span>

1. <span data-ttu-id="a85f8-114">Выберите пароль для шифрования копии главного ключа базы данных, которая будет храниться в базе данных.</span><span class="sxs-lookup"><span data-stu-id="a85f8-114">Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span>
2. <span data-ttu-id="a85f8-115">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a85f8-115">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>
3. <span data-ttu-id="a85f8-116">Разверните узел **Системные базы данных**, щелкните правой кнопкой мыши базу данных `master` и выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a85f8-116">Expand **System Databases**, right-click `master` and then click **New Query**.</span></span>
4. <span data-ttu-id="a85f8-117">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a85f8-117">Copy and paste the following example into the query window and click **Execute**.</span></span>

  ```sql
  -- Creates the master key.
  -- The key is encrypted using the password "23987hxJ#KL95234nl0zBe."
  CREATE MASTER KEY ENCRYPTION BY PASSWORD = '23987hxJ#KL95234nl0zBe';
```

<span data-ttu-id="a85f8-118">Дополнительные сведения см. в разделе [CREATE MASTER KEY (Transact-SQL)](/sql/t-sql/statements/create-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a85f8-118">For more information, see [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql).</span></span>
