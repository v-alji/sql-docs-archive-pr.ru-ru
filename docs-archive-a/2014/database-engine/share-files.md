---
title: Общий доступ к файлам | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sharing files
- file sharing [SQL Server]
- version control services [SQL Server], file sharing
ms.assetid: 645f5c0a-e949-4e87-8988-85e4d6128464
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 79909fcdb09e349798edfe285475f8a898c3bf04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750119"
---
# <a name="share-files"></a><span data-ttu-id="732f4-102">Открытие файлов для общего доступа</span><span class="sxs-lookup"><span data-stu-id="732f4-102">Share Files</span></span>
  <span data-ttu-id="732f4-103">В [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] можно открывать общий доступ к элементам проектов управления версиями.</span><span class="sxs-lookup"><span data-stu-id="732f4-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to share items across source control projects.</span></span> <span data-ttu-id="732f4-104">При совместном использовании элемента все производимые в нем изменения отображаются во всех проектах, для которых открыт общий доступ к данному элементу.</span><span class="sxs-lookup"><span data-stu-id="732f4-104">When you share an item, any changes to the item are reflected in every project to which the item is shared.</span></span>  
  
 <span data-ttu-id="732f4-105">Общий доступ к элементам обеспечивает следующие преимущества для пользователей системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="732f4-105">Item sharing provides the following advantages to source control users:</span></span>  
  
-   <span data-ttu-id="732f4-106">Отпадает необходимость хранить отдельную копию общего элемента для каждого проекта, в котором он используется. Это позволяет экономить место на диске как на клиенте, так и на сервере управления версиями.</span><span class="sxs-lookup"><span data-stu-id="732f4-106">Makes it unnecessary for each project that uses the shared item to store a separate copy of the item, conserving disk space on both the source control client and server.</span></span> <span data-ttu-id="732f4-107">Поставщик управления версиями хранит общий элемент в одном централизованном месте, а каждый проект, имеющий доступ к элементу, содержит указатель на это место.</span><span class="sxs-lookup"><span data-stu-id="732f4-107">The source control provider stores the shared item in one central location, and every project to which it is shared stores a pointer to that location.</span></span>  
  
-   <span data-ttu-id="732f4-108">Предотвращается несовместимость версий.</span><span class="sxs-lookup"><span data-stu-id="732f4-108">Avoids version incompatibilities.</span></span> <span data-ttu-id="732f4-109">Так как каждый проект, который использует элемент, работает с одной и той же версией элемента, предотвращается возможность конфликтов в случае изменения элемента несколькими проектами независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="732f4-109">Because every project to which the item is shared uses the same version of the item, you avoid the conflicts that arise when each copy of an item is changing independently within multiple projects.</span></span>  
  
### <a name="to-share-an-item"></a><span data-ttu-id="732f4-110">Открытие общего доступа к элементу</span><span class="sxs-lookup"><span data-stu-id="732f4-110">To share an item</span></span>  
  
1.  <span data-ttu-id="732f4-111">В обозревателе решений выберите папку или проект, в которых необходимо разместить файлы общего доступа.</span><span class="sxs-lookup"><span data-stu-id="732f4-111">In Solution Explorer, select either the folder or project in which you want to place the shared files.</span></span>  
  
2.  <span data-ttu-id="732f4-112">В меню **файл** укажите пункт **система управления версиями**, а затем выберите пункт **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="732f4-112">On the **File** menu, point to **Source Control**, and then click **Share**.</span></span>  
  
3.  <span data-ttu-id="732f4-113">В диалоговом окне **общий доступ с помощью** найдите в списке Каталог элемент, к которому требуется предоставить общий доступ, и щелкните этот элемент.</span><span class="sxs-lookup"><span data-stu-id="732f4-113">In the **Share with** dialog box, browse the directory list for the item you want to share, and click that item.</span></span>  
  
4.  <span data-ttu-id="732f4-114">Нажмите **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="732f4-114">Click **Share**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="732f4-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="732f4-115">See Also</span></span>  
 [<span data-ttu-id="732f4-116">Основы системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="732f4-116">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
