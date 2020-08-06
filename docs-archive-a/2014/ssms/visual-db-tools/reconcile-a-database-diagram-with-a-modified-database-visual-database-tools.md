---
title: Согласование диаграммы базы данных с измененной базой данных (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- updating diagram to match database
- reconciling database diagrams
- diagrams [SQL Server], reconciling changes
- updating database to match diagram
- database diagrams [SQL Server], reconciling changes
ms.assetid: eda8dea2-eedd-43a7-85aa-92bd97783b5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e5e5127ab613a6f791919a98899e40caa2ddac20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729977"
---
# <a name="reconcile-a-database-diagram-with-a-modified-database-visual-database-tools"></a><span data-ttu-id="8dce2-102">Согласование диаграммы базы данных с измененной базой данных (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="8dce2-102">Reconcile a Database Diagram with a Modified Database (Visual Database Tools)</span></span>
  <span data-ttu-id="8dce2-103">Сохраняйте диаграмму базы данных, когда вы готовы обновить базу данных для согласования с текущей диаграммой.</span><span class="sxs-lookup"><span data-stu-id="8dce2-103">You save your database diagram when you are ready to update the database to match your diagram.</span></span> <span data-ttu-id="8dce2-104">Однако если с момента открытия базы данных другие пользователи внесли изменения в базу данных, то внесенные ими изменения могут повлиять на вашу диаграмму, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="8dce2-104">However, if other users have updated the database since you opened your diagram, their changes might affect your diagram and vice versa.</span></span>  
  
 <span data-ttu-id="8dce2-105">Сохранение диаграммы приводит к согласованию базы данных с диаграммой путем перезаписи изменений, внесенных другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="8dce2-105">Saving your diagram will reconcile the database with your diagram by overwriting other users' changes so that the database will match your diagram.</span></span>  
  
### <a name="to-update-a-database-to-match-your-diagram"></a><span data-ttu-id="8dce2-106">Обновление базы данных для согласования с диаграммой</span><span class="sxs-lookup"><span data-stu-id="8dce2-106">To update a database to match your diagram</span></span>  
  
1.  <span data-ttu-id="8dce2-107">Сохраните диаграмму базы данных.</span><span class="sxs-lookup"><span data-stu-id="8dce2-107">Save your database diagram.</span></span>  
  
     <span data-ttu-id="8dce2-108">Если диаграмма до этого не сохранялась, введите ее имя в диалоговом окне **Сохранение новой диаграммы базы данных** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8dce2-108">If you have not previously saved your diagram, type a name for the diagram in the **Save New Database Diagram** dialog box and choose **OK**.</span></span>  
  
2.  <span data-ttu-id="8dce2-109">В диалоговом окне **Сохранение** перечислены таблицы, которые затронет сохранение диаграммы.</span><span class="sxs-lookup"><span data-stu-id="8dce2-109">The **Save** dialog box lists the tables that will be affected when you save your diagram.</span></span> <span data-ttu-id="8dce2-110">Чтобы продолжить, нажмите кнопку **Да** .</span><span class="sxs-lookup"><span data-stu-id="8dce2-110">Choose **Yes** to continue.</span></span>  
  
3.  <span data-ttu-id="8dce2-111">В диалоговом окне **Обнаружены изменения базы данных** перечислены объекты, в которые были внесены изменения и которые будут исправлены для согласования с диаграммой.</span><span class="sxs-lookup"><span data-stu-id="8dce2-111">The **Database Changes Detected** dialog box lists the objects that were modified and will be changed to match your diagram.</span></span> <span data-ttu-id="8dce2-112">Нажмите кнопку **Да** для сохранения диаграммы и подтверждения всех изменений в списке.</span><span class="sxs-lookup"><span data-stu-id="8dce2-112">Choose **Yes** to save the diagram and accept the list of changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8dce2-113">Если в диаграмме содержатся удаленные из базы данных таблицы и столбцы, то при сохранении диаграммы в базе данных будут повторно созданы только их определения.</span><span class="sxs-lookup"><span data-stu-id="8dce2-113">If your diagram contains tables and columns that were deleted in the database, only their definitions are recreated in the database when you save your diagram.</span></span> <span data-ttu-id="8dce2-114">При этом процессе не восстанавливаются данные, которые существовали в этих объектах до их удаления.</span><span class="sxs-lookup"><span data-stu-id="8dce2-114">This process does not restore any data that existed in these objects before their deletion.</span></span>  
  
### <a name="to-update-your-diagram-to-match-a-modified-database"></a><span data-ttu-id="8dce2-115">Обновление диаграммы для согласования с измененной базой данных</span><span class="sxs-lookup"><span data-stu-id="8dce2-115">To update your diagram to match a modified database</span></span>  
  
1.  <span data-ttu-id="8dce2-116">Закройте диаграмму без сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="8dce2-116">Close your diagram without saving changes.</span></span>  
  
2.  <span data-ttu-id="8dce2-117">Щелкните диаграмму правой кнопкой мыши в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="8dce2-117">Right-click the diagram in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="8dce2-118">В контекстном меню выберите пункт **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="8dce2-118">From the shortcut menu click **Refresh**.</span></span>  
  
4.  <span data-ttu-id="8dce2-119">Снова откройте диаграмму.</span><span class="sxs-lookup"><span data-stu-id="8dce2-119">Reopen the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dce2-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="8dce2-120">See Also</span></span>  
 [<span data-ttu-id="8dce2-121">Работа с диаграммами баз данных (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="8dce2-121">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
