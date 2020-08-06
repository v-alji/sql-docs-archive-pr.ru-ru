---
title: Укажите версию в качестве последней версии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- version control services [SQL Server], latest version
- latest file version specified
- file versions [SQL Server]
ms.assetid: 407dffb1-3ecf-461e-835d-124781f26ee7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: dafe4f757e33a5db63340c3d3cc7c9151871d438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655330"
---
# <a name="specify-a-version-as-the-latest-version"></a><span data-ttu-id="5e02f-102">Указание версии в качестве последней</span><span class="sxs-lookup"><span data-stu-id="5e02f-102">Specify a Version as the Latest Version</span></span>
  <span data-ttu-id="5e02f-103">При регистрации файла в системе управления версиями версия этого файла становится последней. Пользователи, извлекающие последнюю версию, получают локальные копии возвращенного до этого элемента.</span><span class="sxs-lookup"><span data-stu-id="5e02f-103">When you check a file into source control, the version you check in becomes the latest version; users who check out or retrieve the latest version receive local copies of the item most recently checked in.</span></span>  
  
 <span data-ttu-id="5e02f-104">Однако в некоторых ситуациях в качестве последней необходимо назначить более раннюю версию элемента.</span><span class="sxs-lookup"><span data-stu-id="5e02f-104">However, in some situations, you may want to designate an earlier version of an item as the latest version.</span></span> <span data-ttu-id="5e02f-105">Например, было выполнено извлечение файла, его изменение и последующая регистрация.</span><span class="sxs-lookup"><span data-stu-id="5e02f-105">For example, you check out a file, modify the file, and then check the file in.</span></span> <span data-ttu-id="5e02f-106">После этого возникла необходимость отмены изменений.</span><span class="sxs-lookup"><span data-stu-id="5e02f-106">You later decide to discard your modifications.</span></span> <span data-ttu-id="5e02f-107">Так как элемент был возвращен, непосредственная отмена соответствующего исходного извлечения невозможна.</span><span class="sxs-lookup"><span data-stu-id="5e02f-107">Because you have checked in the item, undoing your original checkout is not an option.</span></span> <span data-ttu-id="5e02f-108">В этой ситуации можно назначить исходную извлеченную версию в качестве последней версии элемента.</span><span class="sxs-lookup"><span data-stu-id="5e02f-108">In this situation, you can designate the version you originally checked out as the latest version of the item.</span></span>  
  
 <span data-ttu-id="5e02f-109">Существует несколько способов назначения последней версии.</span><span class="sxs-lookup"><span data-stu-id="5e02f-109">You can designate the latest version by:</span></span>  
  
-   <span data-ttu-id="5e02f-110">**Закрепление версии**.</span><span class="sxs-lookup"><span data-stu-id="5e02f-110">**Pinning a version**.</span></span> <span data-ttu-id="5e02f-111">При закреплении версии файла более поздние версии, чем закрепленная, не удаляются.</span><span class="sxs-lookup"><span data-stu-id="5e02f-111">When you pin a file version, versions that are more recent than the pinned version are not deleted.</span></span> <span data-ttu-id="5e02f-112">Кроме того, можно снять закрепление ранее закрепленного файла.</span><span class="sxs-lookup"><span data-stu-id="5e02f-112">In addition, you can unpin a file that you have previously pinned.</span></span> <span data-ttu-id="5e02f-113">При этом версия файла, возвращенная позже всех, становится последней.</span><span class="sxs-lookup"><span data-stu-id="5e02f-113">When you do this, the most recently checked in version of the file becomes the latest version.</span></span> <span data-ttu-id="5e02f-114">Однако извлечь закрепленный файл невозможно.</span><span class="sxs-lookup"><span data-stu-id="5e02f-114">However, you cannot check out a pinned file.</span></span>  
  
-   <span data-ttu-id="5e02f-115">**Откат к указанной версии**.</span><span class="sxs-lookup"><span data-stu-id="5e02f-115">**Rolling back to a specified version**.</span></span> <span data-ttu-id="5e02f-116">При откате до какой-либо версии все более поздние версии удаляются из системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5e02f-116">When you roll back to a version, all versions more recent than the one to which you have rolled back are deleted from source control.</span></span> <span data-ttu-id="5e02f-117">Затем можно извлечь последнюю из оставшихся версий.</span><span class="sxs-lookup"><span data-stu-id="5e02f-117">You can then check out the latest remaining version.</span></span>  
  
### <a name="to-pin-a-version"></a><span data-ttu-id="5e02f-118">Закрепление версии</span><span class="sxs-lookup"><span data-stu-id="5e02f-118">To pin a version</span></span>  
  
1.  <span data-ttu-id="5e02f-119">Откройте решение в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e02f-119">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="5e02f-120">В обозревателе решений выберите файл, который необходимо назначить в качестве последней версии.</span><span class="sxs-lookup"><span data-stu-id="5e02f-120">In Solution Explorer, select the file that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="5e02f-121">В меню **файл** выберите пункт **система управления версиями** и щелкните **виевхистори**.</span><span class="sxs-lookup"><span data-stu-id="5e02f-121">On the **File** menu, point to **Source Control** and click **ViewHistory**.</span></span>  
  
4.  <span data-ttu-id="5e02f-122">В **History of** \<file> диалоговом окне Журнал выберите версию, которую необходимо указать в качестве последней, и нажмите кнопку **закрепить**.</span><span class="sxs-lookup"><span data-stu-id="5e02f-122">In the **History of** \<file> dialog box, select the version that you want to specify as the latest, and click **Pin**.</span></span>  
  
     <span data-ttu-id="5e02f-123">Возле выбранной версии появится символ закрепления, указывающий, что теперь это текущая версия файла.</span><span class="sxs-lookup"><span data-stu-id="5e02f-123">A pin symbol appears next to the version you have selected, indicating that it is the current file version.</span></span> <span data-ttu-id="5e02f-124">Если в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] загружена другая версия, программа предложит перезагрузить файл.</span><span class="sxs-lookup"><span data-stu-id="5e02f-124">If you have a different version loaded in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you are prompted to reload the file.</span></span>  
  
### <a name="to-roll-back-to-a-version"></a><span data-ttu-id="5e02f-125">Выполнение отката до определенной версии</span><span class="sxs-lookup"><span data-stu-id="5e02f-125">To roll back to a version</span></span>  
  
1.  <span data-ttu-id="5e02f-126">Откройте решение в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e02f-126">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="5e02f-127">В обозревателе решений выберите элемент, который необходимо задать в качестве последней версии.</span><span class="sxs-lookup"><span data-stu-id="5e02f-127">In Solution Explorer, select the item that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="5e02f-128">В меню **файл** укажите пункт **система управления версиями** и выберите пункт **Журнал**.</span><span class="sxs-lookup"><span data-stu-id="5e02f-128">On the **File** menu, point to **Source Control** and click **History**.</span></span>  
  
4.  <span data-ttu-id="5e02f-129">В диалоговом окне **Параметры журнала** нажмите кнопку **ОК** , чтобы открыть диалоговое окно **Журнал файлов** .</span><span class="sxs-lookup"><span data-stu-id="5e02f-129">In the **History Options** dialog box, click **OK** to display the **History of File** dialog box.</span></span>  
  
5.  <span data-ttu-id="5e02f-130">В поле **Журнал файла** выберите версию, которую необходимо указать в качестве последней, и нажмите кнопку **откат**.</span><span class="sxs-lookup"><span data-stu-id="5e02f-130">In the **History of File** box, select the version you want to specify as the latest version, and click **Rollback**.</span></span>  
  
     <span data-ttu-id="5e02f-131">Появится сообщение, уведомляющее о том, что все версии после выбранной будут удалены.</span><span class="sxs-lookup"><span data-stu-id="5e02f-131">A message appears notifying you that all versions subsequent to the one you have selected will be deleted.</span></span>  
  
6.  <span data-ttu-id="5e02f-132">Нажмите кнопку **Да** , чтобы вернуться к выбранной версии.</span><span class="sxs-lookup"><span data-stu-id="5e02f-132">Click **Yes** to roll back to the selected version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e02f-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="5e02f-133">See Also</span></span>  
 <span data-ttu-id="5e02f-134">[Управление возвратами](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="5e02f-134">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="5e02f-135">Возврат файлов</span><span class="sxs-lookup"><span data-stu-id="5e02f-135">Check In Files</span></span>](../../2014/database-engine/check-in-files.md)  
  
  
