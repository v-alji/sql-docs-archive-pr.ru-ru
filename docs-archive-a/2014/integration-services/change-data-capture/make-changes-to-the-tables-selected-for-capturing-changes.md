---
title: Внесение изменений в выбранные для отслеживания изменений таблицы | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- makChanToTab
ms.assetid: a309f82a-c6ef-464d-a6ef-df555bfb609a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 258eb8e761ac697bebd630cc0e627941b4ffc7d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657227"
---
# <a name="make-changes-to-the-tables-selected-for-capturing-changes"></a><span data-ttu-id="0a9f8-102">Внесение изменений в выбранные для отслеживания изменений таблицы</span><span class="sxs-lookup"><span data-stu-id="0a9f8-102">Make Changes to the Tables Selected for Capturing Changes</span></span>
  <span data-ttu-id="0a9f8-103">В этом диалоговом окне можно выбрать столбцы из выбранной таблицы, изменения данных в которых будут отслеживаться.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-103">In this dialog box, you can select specific columns from the selected table to capture changes from.</span></span> <span data-ttu-id="0a9f8-104">Можно также изменить **Роль безопасности** и **Экземпляр отслеживания** .</span><span class="sxs-lookup"><span data-stu-id="0a9f8-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
 <span data-ttu-id="0a9f8-105">В этом диалоговом окне можно выбрать столбцы из выбранной таблицы, изменения данных в которых будут отслеживаться.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-105">You can make the following changes to the tables you selected for capturing changes in this dialog box.</span></span>  
  
 <span data-ttu-id="0a9f8-106">**Изменение списка столбцов, включенных в экземпляр CDC**</span><span class="sxs-lookup"><span data-stu-id="0a9f8-106">**Make changes to which columns are included in the CDC instance:**</span></span>  
  
 <span data-ttu-id="0a9f8-107">Выполните одно из следующих действий (или оба).</span><span class="sxs-lookup"><span data-stu-id="0a9f8-107">Do one or both of the following:</span></span>  
  
-   <span data-ttu-id="0a9f8-108">Установите флажки для всех дополнительных столбцов, которые необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-108">Select the check box next to any additional column you want to include.</span></span>  
  
-   <span data-ttu-id="0a9f8-109">Снимите флажки для тех столбцов, которые необходимо исключить.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-109">Clear the check box next to any column that you no longer want to include.</span></span>  
  
 <span data-ttu-id="0a9f8-110">**Изменить тип данных для определенного столбца**.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-110">**Change the data type for a specific column**:</span></span>  
  
 <span data-ttu-id="0a9f8-111">Для столбца можно выбрать другой тип данных.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-111">You can select a different data type for a specific column.</span></span> <span data-ttu-id="0a9f8-112">В качестве нового типа данных можно выбрать только тип, совместимый с исходным.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-112">You can only change the data type to a data type that is compatible with the original data type.</span></span>  
  
 <span data-ttu-id="0a9f8-113">Чтобы изменить тип данных, щелкните столбец **Тип данных** и выберите другой тип данных.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-113">To change the data type, click in the **Data Type** column and select a different data type.</span></span> <span data-ttu-id="0a9f8-114">Доступны только те типы данных, которые совместимы с исходным.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-114">Only data types that are compatible with the original data type are available.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a9f8-115">Если нельзя выбрать ни одного типа данных, то раскрывающийся список будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-115">If no additional data types can be selected, the drop-down list is not available.</span></span>  
  
 <span data-ttu-id="0a9f8-116">**Изменение роли безопасности**</span><span class="sxs-lookup"><span data-stu-id="0a9f8-116">**Change the Security Role**</span></span>  
  
 <span data-ttu-id="0a9f8-117">Введите новое имя или измените имя роли безопасности в поле **Роль безопасности** .</span><span class="sxs-lookup"><span data-stu-id="0a9f8-117">Type a new name or edit the name of the security gating role in the **Security Role** field.</span></span>  
  
 <span data-ttu-id="0a9f8-118">**Изменение или добавление экземпляра отслеживания**</span><span class="sxs-lookup"><span data-stu-id="0a9f8-118">**Change or add a capture instance**</span></span>  
  
 <span data-ttu-id="0a9f8-119">В поле **Экземпляр отслеживания** введите имя экземпляра отслеживания.</span><span class="sxs-lookup"><span data-stu-id="0a9f8-119">In the **Capture Instance** field enter a name for the capture instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9f8-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a9f8-120">See Also</span></span>  
 <span data-ttu-id="0a9f8-121">[Как создать экземпляр изменения базы данных SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="0a9f8-121">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="0a9f8-122">Выбор таблиц и столбцов Oracle</span><span class="sxs-lookup"><span data-stu-id="0a9f8-122">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
