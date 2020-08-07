---
title: Изменение возвращенных файлов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying checked-in files
- checking in files
ms.assetid: 560cd19f-ab22-4273-b00c-149993a630e6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e2dbe1aad203dfdc83e438d5b7f4ed19c15038c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732958"
---
# <a name="edit-checked-in-files"></a><span data-ttu-id="8a79d-102">Изменение возвращенных файлов</span><span class="sxs-lookup"><span data-stu-id="8a79d-102">Edit Checked-In Files</span></span>
  <span data-ttu-id="8a79d-103">Как правило, прежде чем начать изменение файлов в системе управления версиями, их необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="8a79d-103">You typically must check out source-controlled files before you can edit them.</span></span> <span data-ttu-id="8a79d-104">Однако можно настроить, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] чтобы можно было изменять файлы, которые не были извлечены. При этом изменения сохраняются в памяти до тех пор, пока не будут сохранены файлы.</span><span class="sxs-lookup"><span data-stu-id="8a79d-104">However, you can configure [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] so that you can modify files you have not checked out. When doing so, your changes are held in memory until you save the files.</span></span> <span data-ttu-id="8a79d-105">Затем поступает запрос извлечь файл из системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="8a79d-105">You will then be prompted to check out the file from source control.</span></span>  
  
 <span data-ttu-id="8a79d-106">Если поставщик управления версиями не поддерживает извлечение локальной версии наряду с серверной, при работе в команде разрешать изменение возвращенных файлов не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="8a79d-106">If you work on a team, allowing checked-in files to be edited is not recommended unless your source control provider supports both local version and server version checkouts.</span></span> <span data-ttu-id="8a79d-107">Большинство поставщиков не поддерживает извлечение локальных версий.</span><span class="sxs-lookup"><span data-stu-id="8a79d-107">Most providers do not support local version checkouts.</span></span> <span data-ttu-id="8a79d-108">Если поставщик не поддерживает извлечение локальных версий, то после изменения возвращенного файла придется вручную выполнить слияние версий, хранящихся в памяти и на сервере, прежде чем файл можно будет вернуть.</span><span class="sxs-lookup"><span data-stu-id="8a79d-108">If your provider does not support local version checkouts and you edit a checked-in file, you have to merge the in-memory and server versions manually before the file can be checked in.</span></span> <span data-ttu-id="8a79d-109">Автоматическое слияние и слияние под контролем поставщика в этой ситуации не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8a79d-109">Automatic and provider-assisted merges are unsupported in this situation.</span></span>  
  
### <a name="to-edit-checked-in-files"></a><span data-ttu-id="8a79d-110">Изменение возвращенных файлов</span><span class="sxs-lookup"><span data-stu-id="8a79d-110">To edit checked-in files</span></span>  
  
1.  <span data-ttu-id="8a79d-111">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="8a79d-111">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="8a79d-112">В диалоговом окне **Параметры** раскройте папку **Система управления версиями**, а затем щелкните **Среда**.</span><span class="sxs-lookup"><span data-stu-id="8a79d-112">In the **Options** dialog box, expand the **Source Contro**l folder, and then click **Environment**.</span></span>  
  
3.  <span data-ttu-id="8a79d-113">Выберите **Разрешить изменение возвращенных элементов**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8a79d-113">Click **Allow checked-in items to be edited**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a79d-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a79d-114">See Also</span></span>  
 <span data-ttu-id="8a79d-115">[Управление возвратами](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="8a79d-115">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="8a79d-116">Управление извлечениями</span><span class="sxs-lookup"><span data-stu-id="8a79d-116">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
