---
title: Создание пользовательского псевдонима для типа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.userdefineddatatype.general.f1
- sql12.swb.new.datatype.properties.general.f1
helpviewer_keywords:
- alias data types [SQL Server], creating
ms.assetid: b1dd8413-0cd0-411b-a79b-1bb043ccc62d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35db332c23e2df5a8e67c3677cd2411768816765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654336"
---
# <a name="create-a-user-defined-data-type-alias"></a><span data-ttu-id="b43b0-102">Создание псевдонима определяемого пользователем типа данных</span><span class="sxs-lookup"><span data-stu-id="b43b0-102">Create a User-Defined Data Type Alias</span></span>
  <span data-ttu-id="b43b0-103">В этом разделе описывается создание нового определяемого пользователем псевдонима типа данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b43b0-103">This topic describes how to create a new user-defined data type alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b43b0-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b43b0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b43b0-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="b43b0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b43b0-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b43b0-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b43b0-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b43b0-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b43b0-108">**Создание пользовательского псевдонима типа данных с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="b43b0-108">**To create a user-defined data type alias, using:**</span></span>  
  
     [<span data-ttu-id="b43b0-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b43b0-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b43b0-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b43b0-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b43b0-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b43b0-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b43b0-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b43b0-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b43b0-113">Определяемый пользователем псевдоним типа данных должен соответствовать правилам для идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="b43b0-113">The name of a user-defined data type alias must comply with the rules for identifiers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b43b0-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="b43b0-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b43b0-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="b43b0-115">Permissions</span></span>  
 <span data-ttu-id="b43b0-116">Требует разрешения CREATE TYPE в текущей базе данных и разрешения ALTER для схемы *schema_name*.</span><span class="sxs-lookup"><span data-stu-id="b43b0-116">Requires CREATE TYPE permission in the current database and ALTER permission on *schema_name*.</span></span> <span data-ttu-id="b43b0-117">Если аргумент *schema_name* не указан, в действие вступают принимаемые по умолчанию правила разрешения имен с целью определения схемы для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="b43b0-117">If *schema_name* is not specified, the default name resolution rules for determining the schema for the current user apply.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b43b0-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b43b0-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-user-defined-data-type"></a><span data-ttu-id="b43b0-119">Создание пользовательского типа данных</span><span class="sxs-lookup"><span data-stu-id="b43b0-119">To create a user-defined data type</span></span>  
  
1.  <span data-ttu-id="b43b0-120">Раскройте в обозревателе объектов по очереди узел **Базы данных**, узел конкретной базы данных, узел **Программирование**и **Типы**, щелкните правой кнопкой мыши узел **Определяемые пользователем типы данных**и выберите пункт **Создать определяемый пользователем тип данных**.</span><span class="sxs-lookup"><span data-stu-id="b43b0-120">In Object Explorer, expand **Databases**, expand a database, expand **Programmability**, expand **Types**, right-click **User-Defined Data Types**, and then click **New User-Defined Data Type**.</span></span>  
  
     <span data-ttu-id="b43b0-121">**Разрешить значения NULL**</span><span class="sxs-lookup"><span data-stu-id="b43b0-121">**Allow NULLs**</span></span>  
     <span data-ttu-id="b43b0-122">Указание, допускает ли определяемый пользователем тип данных значения NULL.</span><span class="sxs-lookup"><span data-stu-id="b43b0-122">Specify whether the user-defined data type can accept NULL values.</span></span> <span data-ttu-id="b43b0-123">Допустимость значений NULL для существующего определенного пользователем типа данных не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="b43b0-123">The nullability of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="b43b0-124">**Data type**</span><span class="sxs-lookup"><span data-stu-id="b43b0-124">**Data type**</span></span>  
     <span data-ttu-id="b43b0-125">Выберите базовый тип данных из списка.</span><span class="sxs-lookup"><span data-stu-id="b43b0-125">Select the base data type from the list box.</span></span> <span data-ttu-id="b43b0-126">В списке показаны все типы данных, за исключением типов `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` и `xml`.</span><span class="sxs-lookup"><span data-stu-id="b43b0-126">The list box displays all data types except for the `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` , and `xml` data types.</span></span> <span data-ttu-id="b43b0-127">Тип данных существующего определенного пользователем типа данных не может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="b43b0-127">The data type of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="b43b0-128">**Default**</span><span class="sxs-lookup"><span data-stu-id="b43b0-128">**Default**</span></span>  
     <span data-ttu-id="b43b0-129">При желании можно выбрать правило или значение по умолчанию для привязки к определенному пользователем псевдониму типа данных.</span><span class="sxs-lookup"><span data-stu-id="b43b0-129">Optionally select a rule or a default to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="b43b0-130">**Длина/точность**</span><span class="sxs-lookup"><span data-stu-id="b43b0-130">**Length/Precision**</span></span>  
     <span data-ttu-id="b43b0-131">Отображает длину и точность представления типа данных, где это применимо.</span><span class="sxs-lookup"><span data-stu-id="b43b0-131">Displays the length or precision of the data type as applicable.</span></span> <span data-ttu-id="b43b0-132">Параметр**Длина** применяется к символьным определяемым пользователем типам данных; параметр **Точность** ― только к числовым определяемым пользователем типам данных.</span><span class="sxs-lookup"><span data-stu-id="b43b0-132">**Length** applies to character-based user-defined data types; **Precision** applies only to numeric-based user-defined data types.</span></span> <span data-ttu-id="b43b0-133">Метка изменяется в зависимости от типа данных, выбранного ранее.</span><span class="sxs-lookup"><span data-stu-id="b43b0-133">The label changes depending on the data type selected earlier.</span></span> <span data-ttu-id="b43b0-134">Это поле не редактируется, если длина или точность выбранного элемента данных фиксированы.</span><span class="sxs-lookup"><span data-stu-id="b43b0-134">This box is not editable if the length or precision of the selected data type is fixed.</span></span>  
  
     <span data-ttu-id="b43b0-135">Длина не отображается для типов `nvarchar(max)`, `varchar(max)` и `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="b43b0-135">Length is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
     <span data-ttu-id="b43b0-136">**имя**;</span><span class="sxs-lookup"><span data-stu-id="b43b0-136">**Name**</span></span>  
     <span data-ttu-id="b43b0-137">При создании нового псевдонима определяемого пользователем типа данных введите уникальное имя, которое будет использоваться в базе данных для представления этого псевдонима определяемого пользователем типа данных.</span><span class="sxs-lookup"><span data-stu-id="b43b0-137">If you are creating a new user-defined data type alias, type a unique name to be used across the database to represent the user-defined data type.</span></span> <span data-ttu-id="b43b0-138">Максимальное число символов должно соответствовать системному `sysname` типу данных.</span><span class="sxs-lookup"><span data-stu-id="b43b0-138">The maximum number of characters must match the system `sysname` data type.</span></span> <span data-ttu-id="b43b0-139">Имя существующего псевдонима определяемого пользователем типа данных не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="b43b0-139">The name of an existing user-defined data type alias is not editable.</span></span>  
  
     <span data-ttu-id="b43b0-140">**Правило**</span><span class="sxs-lookup"><span data-stu-id="b43b0-140">**Rule**</span></span>  
     <span data-ttu-id="b43b0-141">При желании выберите правило для привязки к псевдониму определяемого пользователем типа данных.</span><span class="sxs-lookup"><span data-stu-id="b43b0-141">Optionally select a rule to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="b43b0-142">**Масштабирование**</span><span class="sxs-lookup"><span data-stu-id="b43b0-142">**Scale**</span></span>  
     <span data-ttu-id="b43b0-143">Определяет максимальное количество десятичных разрядов, которые могут быть сохранены справа от десятичного разделителя.</span><span class="sxs-lookup"><span data-stu-id="b43b0-143">Specify the maximum number of decimal digits that can be stored to the right of the decimal point.</span></span>  
  
     <span data-ttu-id="b43b0-144">**Схема**</span><span class="sxs-lookup"><span data-stu-id="b43b0-144">**Schema**</span></span>  
     <span data-ttu-id="b43b0-145">Выберите схему из списка всех схем, доступных данному пользователю.</span><span class="sxs-lookup"><span data-stu-id="b43b0-145">Select a schema from a list of all schemas available to the current user.</span></span> <span data-ttu-id="b43b0-146">Выбором по умолчанию является схема по умолчанию для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="b43b0-146">The default selection is the default schema for the current user.</span></span>  
  
     <span data-ttu-id="b43b0-147">**Память**</span><span class="sxs-lookup"><span data-stu-id="b43b0-147">**Storage**</span></span>  
     <span data-ttu-id="b43b0-148">Отображает максимальный размер для псевдонима определяемого пользователем типа данных.</span><span class="sxs-lookup"><span data-stu-id="b43b0-148">Displays the maximum storage size for the user-defined data type alias.</span></span> <span data-ttu-id="b43b0-149">Максимальные размеры хранилища могут быть разными и определяются точностью.</span><span class="sxs-lookup"><span data-stu-id="b43b0-149">Maximum storage sizes vary, based on precision.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="b43b0-150">1–9</span><span class="sxs-lookup"><span data-stu-id="b43b0-150">1 - 9</span></span>|<span data-ttu-id="b43b0-151">5</span><span class="sxs-lookup"><span data-stu-id="b43b0-151">5</span></span>|  
    |<span data-ttu-id="b43b0-152">10–19</span><span class="sxs-lookup"><span data-stu-id="b43b0-152">10 - 19</span></span>|<span data-ttu-id="b43b0-153">9</span><span class="sxs-lookup"><span data-stu-id="b43b0-153">9</span></span>|  
    |<span data-ttu-id="b43b0-154">20–28</span><span class="sxs-lookup"><span data-stu-id="b43b0-154">20 - 28</span></span>|<span data-ttu-id="b43b0-155">13</span><span class="sxs-lookup"><span data-stu-id="b43b0-155">13</span></span>|  
    |<span data-ttu-id="b43b0-156">29–38</span><span class="sxs-lookup"><span data-stu-id="b43b0-156">29 - 38</span></span>|<span data-ttu-id="b43b0-157">17</span><span class="sxs-lookup"><span data-stu-id="b43b0-157">17</span></span>|  
  
     <span data-ttu-id="b43b0-158">Для `nchar` `nvarchar` типов данных и значение хранилища всегда в два раза больше значения в параметре **length**.</span><span class="sxs-lookup"><span data-stu-id="b43b0-158">For `nchar` and `nvarchar` data types, the storage value is always two times the value in **Length**.</span></span>  
  
     <span data-ttu-id="b43b0-159">Значение хранилища не отображается для типов данных `nvarchar(max)`, `varchar(max)` и `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="b43b0-159">Storage is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
2.  <span data-ttu-id="b43b0-160">В диалоговом окне **Создание определяемого пользователем типа данных** введите в поле **Схема** схему, которая будет владеть новым псевдонимом типа данных, или выберите схему, нажав кнопку обзора.</span><span class="sxs-lookup"><span data-stu-id="b43b0-160">In the **New User-defined Data Type** dialog box, in the **Schema** box, type the schema to own this data type alias, or use the browse button to select the schema.</span></span>  
  
3.  <span data-ttu-id="b43b0-161">В поле **Имя** введите имя нового псевдонима типа данных.</span><span class="sxs-lookup"><span data-stu-id="b43b0-161">In the **Name** box, type a name for the new data type alias.</span></span>  
  
4.  <span data-ttu-id="b43b0-162">В поле **Тип данных** выберите тип, на основе которого будет создан новый псевдоним типа данных.</span><span class="sxs-lookup"><span data-stu-id="b43b0-162">In the **Data type** box, select the data type that the new data type alias will be based on.</span></span>  
  
5.  <span data-ttu-id="b43b0-163">Заполните поля **Длина**, **Точность**и **Масштаб** , если это требуется для создаваемого типа данных.</span><span class="sxs-lookup"><span data-stu-id="b43b0-163">Complete the **Length**, **Precision**, and **Scale** boxes if appropriate for that data type.</span></span>  
  
6.  <span data-ttu-id="b43b0-164">Если новый псевдоним типа данных должен поддерживать значения NULL, установите флажок **Разрешить значения NULL** .</span><span class="sxs-lookup"><span data-stu-id="b43b0-164">Check **Allow NULLs** if the new data type alias can permit NULL values.</span></span>  
  
7.  <span data-ttu-id="b43b0-165">Если требуется связать с новым псевдонимом типа данных значение по умолчанию или правило, заполните в области **Привязка** поле **По умолчанию** или **Правило** .</span><span class="sxs-lookup"><span data-stu-id="b43b0-165">In the **Binding** area, complete the **Default** or **Rule** boxes if you want to bind a default or rule to the new data type alias.</span></span> <span data-ttu-id="b43b0-166">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]нельзя создавать правила или значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b43b0-166">Defaults and rules cannot be created in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b43b0-167">Используйте [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b43b0-167">Use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b43b0-168">Примеры кода, создающего умолчания и правила, доступны в окне обозревателя шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b43b0-168">Example code for creating defaults and rules are available in Template Explorer.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b43b0-169">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b43b0-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-user-defined-data-type-alias"></a><span data-ttu-id="b43b0-170">Создание псевдонима определяемого пользователем типа данных</span><span class="sxs-lookup"><span data-stu-id="b43b0-170">To create a user-defined data type alias</span></span>  
  
1.  <span data-ttu-id="b43b0-171">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b43b0-171">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b43b0-172">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b43b0-172">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b43b0-173">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b43b0-173">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b43b0-174">В следующем примере создается псевдоним типа данных на базе определенного в системе типа данных `varchar` .</span><span class="sxs-lookup"><span data-stu-id="b43b0-174">This example creates a data type alias based on the system-supplied `varchar` data type.</span></span> <span data-ttu-id="b43b0-175">Псевдоним типа данных `ssn` используется для столбцов, хранящих номера карточек социального страхования, состоящих из 11 разрядов (999-99-9999).</span><span class="sxs-lookup"><span data-stu-id="b43b0-175">The `ssn` data type alias is used for columns holding 11-digit social security numbers (999-99-9999).</span></span> <span data-ttu-id="b43b0-176">Эти столбцы не могут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b43b0-176">The column cannot be NULL.</span></span>  
  
```sql  
CREATE TYPE ssn  
FROM varchar(11) NOT NULL ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="b43b0-177">См. также:</span><span class="sxs-lookup"><span data-stu-id="b43b0-177">See Also</span></span>  
 <span data-ttu-id="b43b0-178">[Идентификаторы баз данных](database-identifiers.md) </span><span class="sxs-lookup"><span data-stu-id="b43b0-178">[Database Identifiers](database-identifiers.md) </span></span>  
 [<span data-ttu-id="b43b0-179">CREATE TYPE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b43b0-179">CREATE TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-type-transact-sql)  
  
  
