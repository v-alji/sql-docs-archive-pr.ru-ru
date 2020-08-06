---
title: Изменение свойств таблицы | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- editTabProps
ms.assetid: 95ea72ba-8e40-4177-a963-0fb4d10c56e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1ba0809b99474704ec0e93e417a04d776bb26d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657232"
---
# <a name="edit-the-table-properties"></a><span data-ttu-id="e9297-102">Изменение свойств таблицы</span><span class="sxs-lookup"><span data-stu-id="e9297-102">Edit the Table Properties</span></span>
  <span data-ttu-id="e9297-103">Это диалоговое окно служит для изменения столбцов из выбранной таблицы, для которой производится отслеживание изменений.</span><span class="sxs-lookup"><span data-stu-id="e9297-103">Use this dialog box to edit the specific columns from the selected table where changes are being captured.</span></span> <span data-ttu-id="e9297-104">Можно также изменить **Роль безопасности** и **Экземпляр отслеживания** .</span><span class="sxs-lookup"><span data-stu-id="e9297-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
### <a name="to-edit-the-columns-to-include-in-the-cdc-instance"></a><span data-ttu-id="e9297-105">Изменение столбцов, включаемых в экземпляр CDC</span><span class="sxs-lookup"><span data-stu-id="e9297-105">To edit the columns to include in the CDC instance</span></span>  
  
1.  <span data-ttu-id="e9297-106">Выполните одно из следующих действий (или оба).</span><span class="sxs-lookup"><span data-stu-id="e9297-106">Do one or both of the following:</span></span>  
  
    -   <span data-ttu-id="e9297-107">Установите флажки для всех дополнительных столбцов, которые необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="e9297-107">Select the check box next to any additional column you want to include.</span></span>  
  
    -   <span data-ttu-id="e9297-108">Снимите флажки для тех столбцов, которые необходимо исключить.</span><span class="sxs-lookup"><span data-stu-id="e9297-108">Clear the check box next to any column that you no longer want to include.</span></span>  
  
### <a name="to-edit-the-security-role"></a><span data-ttu-id="e9297-109">Изменение роли безопасности</span><span class="sxs-lookup"><span data-stu-id="e9297-109">To edit the Security Role</span></span>  
  
1.  <span data-ttu-id="e9297-110">Введите новое имя или измените имя роли безопасности в поле **Роль безопасности** .</span><span class="sxs-lookup"><span data-stu-id="e9297-110">Type a new name or edit the name of the security role in the **Security Role** field.</span></span>  
  
### <a name="to-create-a-new-capture-instance"></a><span data-ttu-id="e9297-111">Создание нового экземпляра отслеживания</span><span class="sxs-lookup"><span data-stu-id="e9297-111">To create a new capture instance</span></span>  
  
1.  <span data-ttu-id="e9297-112">В разделе **Роль безопасности** введите имя экземпляра отслеживания в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="e9297-112">In the **Security Role** section, **Name** field enter a name for the capture instance.</span></span> <span data-ttu-id="e9297-113">По умолчанию в этом поле указано имя текущего экземпляра отслеживания, в конец которого добавляется суффикс **_NEW** (например, **старый_экземпляр_NEW**).</span><span class="sxs-lookup"><span data-stu-id="e9297-113">By default, the name entered in the field is the name of the current capture instance with **_NEW** added to the end of the name (for example, **old_instance_NEW**).</span></span>  
  
2.  <span data-ttu-id="e9297-114">Сохраните экземпляр отслеживания как один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="e9297-114">Save the capture instance as one of the following:</span></span>  
  
    -   <span data-ttu-id="e9297-115">**Новый экземпляр отслеживания**. В этом случае новый экземпляр отслеживания сохраняется, а старый не удаляется.</span><span class="sxs-lookup"><span data-stu-id="e9297-115">**New Capture Instance**: In this case a new capture instance is saved and the old capture instance is not deleted.</span></span>  
  
         <span data-ttu-id="e9297-116">**Примечание**. Для одной таблицы может быть не больше двух экземпляров отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e9297-116">**Note**: You can have no more than two capture instances per table.</span></span> <span data-ttu-id="e9297-117">Если уже есть два экземпляра отслеживания, то этот вариант будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="e9297-117">If there are already two capture instances, this option is not available.</span></span>  
  
    -   <span data-ttu-id="e9297-118">**Замена существующего экземпляра**. В этом случае текущий экземпляр отслеживания удаляется и заменяется созданным экземпляром.</span><span class="sxs-lookup"><span data-stu-id="e9297-118">**Replace Existing**: In this case the current capture instance is deleted and replaced by the capture instance you created.</span></span> <span data-ttu-id="e9297-119">Если для этой таблицы уже созданы два экземпляра отслеживания, то необходимо выбрать один из них для замены.</span><span class="sxs-lookup"><span data-stu-id="e9297-119">If there are two capture instances defined for this table, you must select one to replace.</span></span>  
  
 <span data-ttu-id="e9297-120">**Примечание**. Экземпляр отслеживания можно удалить из списка таблиц на вкладке **Таблица** .</span><span class="sxs-lookup"><span data-stu-id="e9297-120">**Note**: You can remove a capture instance from the list of tables in the **Table** tab.</span></span>  
  
 <span data-ttu-id="e9297-121">После окончания ввода данных в этом диалоговом окне нажмите кнопку **ОК** , чтобы принять изменения.</span><span class="sxs-lookup"><span data-stu-id="e9297-121">After you finish entering the information in this dialog box, click **OK** to accept the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9297-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9297-122">See Also</span></span>  
 <span data-ttu-id="e9297-123">[Как изменить свойства экземпляра CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e9297-123">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="e9297-124">Внесение изменений в выбранные для отслеживания изменений таблицы</span><span class="sxs-lookup"><span data-stu-id="e9297-124">Make Changes to the Tables Selected for Capturing Changes</span></span>](make-changes-to-the-tables-selected-for-capturing-changes.md)  
  
  
