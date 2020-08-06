---
title: Папка моментальных снимков | Документация Майкрософт
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.specifysnapshotfolder.f1
ms.assetid: 3eb1b73f-ddb3-4d09-be6e-811c414698e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48b490c65662edf65018e98dd1bc3339f6aae6b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668755"
---
# <a name="snapshot-folder"></a><span data-ttu-id="5de5b-102">Папка моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="5de5b-102">Snapshot Folder</span></span>
  <span data-ttu-id="5de5b-103">Страница **Папка моментальных снимков** отображается в мастере настройки распространителя и мастере создания публикаций.</span><span class="sxs-lookup"><span data-stu-id="5de5b-103">The **Snapshot Folder** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="5de5b-104">Заданное вами местоположение для папки моментальных снимков будет использоваться по умолчанию для всех издателей, включенных данным мастером (папка моментальных снимков по умолчанию не используется для издателей, включенных позднее с использованием диалогового окна **Свойства распространителя** ).</span><span class="sxs-lookup"><span data-stu-id="5de5b-104">The location you specify for the snapshot folder will be used as the default for all Publishers enabled in this wizard (the default snapshot folder does not apply to Publishers that are later enabled using the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="5de5b-105">Это значение по умолчанию можно заменить для любого издателя на странице **Издатели** мастера настройки распространителя или диалогового окна **Свойства распространителя** .</span><span class="sxs-lookup"><span data-stu-id="5de5b-105">You can override this default for any Publisher on the **Publishers** page of the Configure Distribution Wizard or the **Distributor Properties** dialog box.</span></span>  
  
 <span data-ttu-id="5de5b-106">Папка моментальных снимков — это просто каталог, назначенный для совместного использования; агенты, считывающие и записывающие данные в эту папку, должны иметь достаточные разрешения для доступа к ней.</span><span class="sxs-lookup"><span data-stu-id="5de5b-106">The snapshot folder is simply a directory that you have designated as a share; agents that read from and write to this folder must have sufficient permissions to access it.</span></span> <span data-ttu-id="5de5b-107">Дополнительные сведения о надлежащей защите папок см. в статье [Организация безопасности папки моментальных снимков](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="5de5b-107">For more information about securing the folder appropriately, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span> <span data-ttu-id="5de5b-108">До реализации репликации необходимо убедиться, что агенты репликации смогут подключиться к папке моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="5de5b-108">Prior to implementing replication, test that the replication agents will be able to connect to the snapshot folder.</span></span> <span data-ttu-id="5de5b-109">Войдите в систему с учетной записью, которая будет использоваться каждым агентом, и попытайтесь получить доступ к папке моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="5de5b-109">Log on under the account that will be used by each agent and then attempt to access the snapshot folder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5de5b-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="5de5b-110">Options</span></span>  
 <span data-ttu-id="5de5b-111">**Папка моментальных снимков**</span><span class="sxs-lookup"><span data-stu-id="5de5b-111">**Snapshot folder**</span></span>  
 <span data-ttu-id="5de5b-112">Введите путь к папке, в которой будет храниться моментальный снимок.</span><span class="sxs-lookup"><span data-stu-id="5de5b-112">Enter the path for the folder where you want snapshot files stored.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="5de5b-113">рекомендует настроить совместно используемую сетевую папку в качестве местоположения папки моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="5de5b-113">recommends that you use a network share as a snapshot folder location.</span></span> <span data-ttu-id="5de5b-114">Локальные пути (начинающиеся с буквы диска, например C:\\) недоступны агентам с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="5de5b-114">Local paths (those starting with a drive letter, such as C:\\) are not accessible to agents on other computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de5b-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="5de5b-115">See Also</span></span>  
 <span data-ttu-id="5de5b-116">[Альтернативные расположения папки моментальных снимков](alternate-snapshot-folder-locations.md) </span><span class="sxs-lookup"><span data-stu-id="5de5b-116">[Alternate Snapshot Folder Locations](alternate-snapshot-folder-locations.md) </span></span>  
 <span data-ttu-id="5de5b-117">[Настройка распространения](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="5de5b-117">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="5de5b-118">[Настройка публикации и распространения](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="5de5b-118">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="5de5b-119">[Просмотр и изменение свойств издателя и распространителя](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="5de5b-119">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="5de5b-120">Инициализация подписки с помощью моментального снимка</span><span class="sxs-lookup"><span data-stu-id="5de5b-120">Initialize a Subscription with a Snapshot</span></span>](initialize-a-subscription-with-a-snapshot.md)  
  
  
