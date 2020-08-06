---
title: Добавление и удаление статей в публикации (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], dropping
- deleting articles
- dropping articles
- adding articles
- articles [SQL Server replication], adding
ms.assetid: d5a3e536-62d2-4473-a178-877ba52f7d7f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7af1cac1f3ee8ecc9cb79632f8a4ef1e66ec82f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668786"
---
# <a name="add-articles-to-and-drop-articles-from-a-publication-sql-server-management-studio"></a><span data-ttu-id="55ae5-102">Добавление и удаление статей в публикации (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="55ae5-102">Add Articles to and Drop Articles from a Publication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="55ae5-103">Вначале статьи в публикацию добавляются при ее создании в мастере создания публикации.</span><span class="sxs-lookup"><span data-stu-id="55ae5-103">Initially add articles to a publication when you create it in the New Publication Wizard.</span></span> <span data-ttu-id="55ae5-104">Дополнительные сведения об использовании мастера см. в статье [Создание публикации](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="55ae5-104">For more information about using this wizard, see [Create a Publication](create-a-publication.md).</span></span>  
  
 <span data-ttu-id="55ae5-105">После создания публикации вы можете добавлять и удалять статьи на странице **Статьи** диалогового окна **Свойства публикации — \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="55ae5-105">After a publication is created, add and delete articles on the **Articles** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="55ae5-106">Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Просмотр и изменение свойств публикации](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="55ae5-106">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="55ae5-107">Сведения о добавлении и удалении статей см. в статье [Добавление и удаление статей в существующих публикациях](add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="55ae5-107">For information about the considerations for adding and dropping articles, see [Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
### <a name="to-add-an-article-after-a-publication-is-created"></a><span data-ttu-id="55ae5-108">Добавление статьи после создания публикации</span><span class="sxs-lookup"><span data-stu-id="55ae5-108">To add an article after a publication is created</span></span>  
  
1.  <span data-ttu-id="55ae5-109">На странице **Статьи** диалогового окна **Свойства публикации — \<Publication>** снимите флажок **Показывать в списке только отмеченные объекты**.</span><span class="sxs-lookup"><span data-stu-id="55ae5-109">On the **Articles** page of the **Publication Properties - \<Publication>** dialog box, clear the **Show only checked objects in the list** check box.</span></span> <span data-ttu-id="55ae5-110">Это позволит увидеть неопубликованные объекты в базе данных публикаций.</span><span class="sxs-lookup"><span data-stu-id="55ae5-110">This allows you to see the unpublished objects in the publication database.</span></span>  
  
2.  <span data-ttu-id="55ae5-111">Установите флажок рядом с каждой статьей, которую нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="55ae5-111">Select the check box next to each article you want to add.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-an-article"></a><span data-ttu-id="55ae5-112">Удаление статьи</span><span class="sxs-lookup"><span data-stu-id="55ae5-112">To delete an article</span></span>  
  
1.  <span data-ttu-id="55ae5-113">На странице **Статьи** диалогового окна **Свойства публикации — \<Publication>** снимите флажки напротив всех статей, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="55ae5-113">On the **Articles** page of the **Publication Properties - \<Publication>** dialog box, clear the check box next to each article you want to delete.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="55ae5-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="55ae5-114">See Also</span></span>  
 <span data-ttu-id="55ae5-115">[Define an Article](define-an-article.md) </span><span class="sxs-lookup"><span data-stu-id="55ae5-115">[Define an Article](define-an-article.md) </span></span>  
 [<span data-ttu-id="55ae5-116">Публикация данных и объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="55ae5-116">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  
