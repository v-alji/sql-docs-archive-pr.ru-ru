---
title: Страница «Создание папки» (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9212fc68-f0a6-4f79-83c1-84baf4d1957e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 27c6a82c4911ba42215d4ab7dcafd666ddce5d54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666459"
---
# <a name="new-folder-page-report-manager"></a><span data-ttu-id="a7909-102">Страница «Создать папку» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="a7909-102">New Folder Page (Report Manager)</span></span>
  <span data-ttu-id="a7909-103">На странице «Создание папки» можно создать новую папку в иерархии папок сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a7909-103">Use the New Folder page to create a new folder in the report server folder hierarchy.</span></span> <span data-ttu-id="a7909-104">Создается виртуальная папка, сохраняемая в базу данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a7909-104">The folder that you create is a virtual folder that is stored in a report server database.</span></span> <span data-ttu-id="a7909-105">а в файловой системе компьютера папки не создается.</span><span class="sxs-lookup"><span data-stu-id="a7909-105">The folder is not created in the file system of your computer.</span></span>  
  
 <span data-ttu-id="a7909-106">Папка создается как вложенная в выделенную в данный момент папку.</span><span class="sxs-lookup"><span data-stu-id="a7909-106">A folder is created in-place, as a subfolder of the folder that is currently selected.</span></span> <span data-ttu-id="a7909-107">Перед созданием папки необходимо перейти к тому месту, где она должна располагаться.</span><span class="sxs-lookup"><span data-stu-id="a7909-107">Before creating a folder, you should navigate to the location where you want to create the folder.</span></span>  
  
 <span data-ttu-id="a7909-108">После того как папка создана, можно изменить ее имя и описание на странице «Общие свойства» папки.</span><span class="sxs-lookup"><span data-stu-id="a7909-108">After you create a folder, you can modify its name and description through the General properties page of the folder.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="a7909-109">Навигация</span><span class="sxs-lookup"><span data-stu-id="a7909-109">Navigation</span></span>  
 <span data-ttu-id="a7909-110">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="a7909-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-folder-page"></a><span data-ttu-id="a7909-111">Открытие страницы «Создать папку»</span><span class="sxs-lookup"><span data-stu-id="a7909-111">To open the New Folder page</span></span>  
  
1.  <span data-ttu-id="a7909-112">Откройте диспетчер отчетов и перейдите к папке, в которой необходимо создать новую папку.</span><span class="sxs-lookup"><span data-stu-id="a7909-112">Open Report Manager, and navigate to the folder in which you want to create a new folder.</span></span>  
  
2.  <span data-ttu-id="a7909-113">На панели инструментов нажмите кнопку **Создать папку**.</span><span class="sxs-lookup"><span data-stu-id="a7909-113">In the toolbar, click **New Folder**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a7909-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7909-114">Options</span></span>  
 <span data-ttu-id="a7909-115">**имя**;</span><span class="sxs-lookup"><span data-stu-id="a7909-115">**Name**</span></span>  
 <span data-ttu-id="a7909-116">Укажите имя папки.</span><span class="sxs-lookup"><span data-stu-id="a7909-116">Specify the name of the folder.</span></span> <span data-ttu-id="a7909-117">Имя должно содержать хотя бы одну букву или цифру.</span><span class="sxs-lookup"><span data-stu-id="a7909-117">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="a7909-118">Оно также может включать пробелы и специальные знаки.</span><span class="sxs-lookup"><span data-stu-id="a7909-118">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="a7909-119">Не используйте символы ; ?</span><span class="sxs-lookup"><span data-stu-id="a7909-119">Do not use the characters ; ?</span></span> <span data-ttu-id="a7909-120">: \@ & = +, $/\* \< > | "или/при указании имени.</span><span class="sxs-lookup"><span data-stu-id="a7909-120">: \@ & = + , $ / \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="a7909-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a7909-121">**Description**</span></span>  
 <span data-ttu-id="a7909-122">Введите описание содержимого папки.</span><span class="sxs-lookup"><span data-stu-id="a7909-122">Type a description of folder contents.</span></span> <span data-ttu-id="a7909-123">Описание появится на странице «Содержимое» у тех пользователей, которые имеют доступ к папке.</span><span class="sxs-lookup"><span data-stu-id="a7909-123">This description appears in the Contents page to users who have permission to access the folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7909-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7909-124">See Also</span></span>  
 <span data-ttu-id="a7909-125">[Создание, удаление и изменение папки &#40;диспетчер отчетов&#41;](report-server/create-delete-or-modify-a-folder-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a7909-125">[Create, Delete, or Modify a Folder &#40;Report Manager&#41;](report-server/create-delete-or-modify-a-folder-report-manager.md) </span></span>  
 <span data-ttu-id="a7909-126">[Страница «Общие свойства», папки &#40;диспетчер отчетов&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a7909-126">[General Properties Page, Folders &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span></span>  
 <span data-ttu-id="a7909-127">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="a7909-127">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="a7909-128">[Страница "содержимое" &#40;диспетчер отчетов&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a7909-128">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="a7909-129">[Справка F1 диспетчер отчетов](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="a7909-129">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="a7909-130">Страница «Общие свойства», папки &#40;диспетчер отчетов&#41;</span><span class="sxs-lookup"><span data-stu-id="a7909-130">General Properties Page, Folders &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/general-properties-page-folders-report-manager.md)  
  
  
