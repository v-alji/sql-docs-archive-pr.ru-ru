---
title: Удаление объектов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.deleteobjects.f1
helpviewer_keywords:
- Delete Objects dialog box
ms.assetid: 49541441-179c-40d3-ba0c-01bcae545984
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7b20d1eee3e48c5531b6b788e125b943f7606d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654032"
---
# <a name="delete-objects"></a><span data-ttu-id="559d9-102">Удаление объектов</span><span class="sxs-lookup"><span data-stu-id="559d9-102">Delete Objects</span></span>
  <span data-ttu-id="559d9-103">Используйте данное диалоговое окно для удаления базы данных или объекта базы данных.</span><span class="sxs-lookup"><span data-stu-id="559d9-103">Use this dialog box to delete a database or database object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="559d9-104">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="559d9-104">UI element list</span></span>  
 <span data-ttu-id="559d9-105">**Объект для удаления**</span><span class="sxs-lookup"><span data-stu-id="559d9-105">**Object to be deleted**</span></span>  
 <span data-ttu-id="559d9-106">Отображаются имена, типы, владельцы и состояние объектов, которые будут удалены, а также любые сообщения об ошибках во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="559d9-106">Displays the names, types, owners, and status of the objects that are about to be deleted, as well as any messages about errors during execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="559d9-107">Команда **Удалить** , применяемая к базе данных, соответствует команде DROP DATABASE в [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="559d9-107">Running **Delete** on a database is equivalent to issuing DROP DATABASE in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="559d9-108">**Показать зависимости**</span><span class="sxs-lookup"><span data-stu-id="559d9-108">**Show Dependencies**</span></span>  
 <span data-ttu-id="559d9-109">Нажмите, чтобы отобразить объекты, зависимые от выбранного объекта, и объекты, от которых зависит выбранный объект (восходящая или нисходящая зависимость).</span><span class="sxs-lookup"><span data-stu-id="559d9-109">Click to display both the objects that are dependent on the currently selected object and objects that the current object is dependent on (upward and downward dependency).</span></span> <span data-ttu-id="559d9-110">Данные, отображаемые в диалоговом окне **Показать зависимости** , доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="559d9-110">The information displayed in the **Show Dependencies** dialog box is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="559d9-111">Не для всех типов объектов базы данных отображается кнопка **Показать зависимости** .</span><span class="sxs-lookup"><span data-stu-id="559d9-111">The **Show Dependencies** button does not appear for all types of database objects.</span></span> <span data-ttu-id="559d9-112">Чтобы просмотреть зависимости при отсутствии кнопки **Показать зависимости** , щелкните правой кнопкой мыши объект в обозревателе объектов и выберите в контекстном меню пункт **Просмотреть зависимости**.</span><span class="sxs-lookup"><span data-stu-id="559d9-112">To view dependencies when the **Show Dependencies** button is not available, right-click the object in Object Explorer, and then click **View Dependencies**.</span></span>  
  
 <span data-ttu-id="559d9-113">**Удалить журналы резервного копирования и восстановления баз данных**</span><span class="sxs-lookup"><span data-stu-id="559d9-113">**Delete backup and restore history information for databases**</span></span>  
 <span data-ttu-id="559d9-114">Данный флажок отображается только после удаления базы данных и вызывает удаление журнала резервного копирования и восстановления объектной базы данных из базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="559d9-114">Only appears when a database is deleted, this check box causes the backup and restore history for the subject database to be deleted from the **msdb** database.</span></span>  
  
 <span data-ttu-id="559d9-115">**Закрыть существующие соединения**</span><span class="sxs-lookup"><span data-stu-id="559d9-115">**Close existing connections**</span></span>  
 <span data-ttu-id="559d9-116">Флажок отображается только после удаления базы данных и используется для закрытия соединения с базой данных.</span><span class="sxs-lookup"><span data-stu-id="559d9-116">Only appears when a database is deleted, this check box terminates connections to the subject database.</span></span>  
  
  
