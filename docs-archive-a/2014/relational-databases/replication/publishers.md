---
title: Издатели | Документация Майкрософт
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.enablepublishers.f1
ms.assetid: 116cd6a5-32ac-4273-81a2-d184408e0f07
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 879fa3cc2ecadf56914928c6ae83600f513f6ddb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654150"
---
# <a name="publishers"></a><span data-ttu-id="06352-102">Издатели</span><span class="sxs-lookup"><span data-stu-id="06352-102">Publishers</span></span>
  <span data-ttu-id="06352-103">Можно разрешить другим издателям использовать этот распространитель.</span><span class="sxs-lookup"><span data-stu-id="06352-103">You can give permission for other Publishers to use this Distributor.</span></span> <span data-ttu-id="06352-104">Учтите, что разрешение для издателя использовать данный сервер в качестве своего удаленного распространителя не превращает данный сервер в издатель.</span><span class="sxs-lookup"><span data-stu-id="06352-104">Be aware that enabling a Publisher to use this server as its remote Distributor does not make that server a Publisher.</span></span> <span data-ttu-id="06352-105">Необходимо подключиться к издателю, настроить его для публикации и выбрать этот сервер в качестве распространителя.</span><span class="sxs-lookup"><span data-stu-id="06352-105">You must connect to the Publisher, configure it for publishing, and choose this server as the Distributor.</span></span> <span data-ttu-id="06352-106">Возможна настройка издателя и выбор распространителя с помощью мастера создания публикаций.</span><span class="sxs-lookup"><span data-stu-id="06352-106">You can configure the Publisher and choose a Distributor through the New Publication Wizard.</span></span>  
  
 <span data-ttu-id="06352-107">Серверы, выбранные в качестве издателей, будут использовать базу данных распространителя, указанную на странице **База данных распространителя** данного мастера.</span><span class="sxs-lookup"><span data-stu-id="06352-107">The servers you select as Publishers will use the distribution database specified on the **Distribution Database** page of this wizard.</span></span> <span data-ttu-id="06352-108">Если нужно использовать другую базу данных распространителя, не включайте издатель сейчас.</span><span class="sxs-lookup"><span data-stu-id="06352-108">If you want to use a different distribution database, do not enable the Publisher at this time.</span></span> <span data-ttu-id="06352-109">Вместо этого используйте для добавления издателей диалоговое окно **Свойства распространителя** после завершения работы мастера настройки распространения.</span><span class="sxs-lookup"><span data-stu-id="06352-109">Instead, use the **Distributor Properties** dialog box to add Publishers after you complete the Configure Distribution Wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="06352-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="06352-110">Options</span></span>  
 <span data-ttu-id="06352-111">**Издатели**</span><span class="sxs-lookup"><span data-stu-id="06352-111">**Publishers**</span></span>  
 <span data-ttu-id="06352-112">Выберите серверы, которым разрешено использование данного распространителя.</span><span class="sxs-lookup"><span data-stu-id="06352-112">Select the servers that are allowed to use this Distributor.</span></span> <span data-ttu-id="06352-113">Нажмите кнопку свойств ( **...** ) рядом с издателем для просмотра и задания дополнительных свойств.</span><span class="sxs-lookup"><span data-stu-id="06352-113">Click the properties button (**...**) next to a Publisher to view and set additional properties.</span></span>  
  
 <span data-ttu-id="06352-114">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="06352-114">**Add**</span></span>  
 <span data-ttu-id="06352-115">Если нужный сервер не представлен в списке, нажмите кнопку **Добавить**, чтобы добавить издателей [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или Oracle к списку доступных издателей.</span><span class="sxs-lookup"><span data-stu-id="06352-115">If the server you want to allow is not listed, click **Add** to add a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher or Oracle Publisher to the list of available Publishers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06352-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="06352-116">See Also</span></span>  
 <span data-ttu-id="06352-117">[Настройка распространения](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="06352-117">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="06352-118">[Настройка публикации и распространения](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="06352-118">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="06352-119">[Просмотр и изменение свойств издателя и распространителя](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="06352-119">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="06352-120">Create a Publication</span><span class="sxs-lookup"><span data-stu-id="06352-120">Create a Publication</span></span>](publish/create-a-publication.md)  
  
  
