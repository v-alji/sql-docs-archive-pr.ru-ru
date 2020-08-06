---
title: Страница "Общие свойства", папки (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 31d99d9b-2303-4bae-9466-fb67b97cf11a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb1c3fbf2e9020ac5d1fe5ebbd1e9ed48b45adb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668111"
---
# <a name="general-properties-page-folders-report-manager"></a><span data-ttu-id="812a9-102">Страница свойств «Общие», папки (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="812a9-102">General Properties Page, Folders (Report Manager)</span></span>
  <span data-ttu-id="812a9-103">Для просмотра и установки свойств для создаваемых папок используется страница «Общие свойства».</span><span class="sxs-lookup"><span data-stu-id="812a9-103">Use the General properties page for folders to view and set properties for the folders that you create.</span></span> <span data-ttu-id="812a9-104">Данные о том, кто создал или изменил папку, а также о времени изменения папки отображаются в верхней части страницы свойств «Общие».</span><span class="sxs-lookup"><span data-stu-id="812a9-104">Information about who created or modified the folder and when the folder was modified appear at the top of the General properties page.</span></span>  
  
 <span data-ttu-id="812a9-105">Свойства папки включают также настройки безопасности.</span><span class="sxs-lookup"><span data-stu-id="812a9-105">Folder properties also include security settings.</span></span> <span data-ttu-id="812a9-106">Дополнительные сведения о безопасности папок см. в разделе [защита папок](security/secure-folders.md).</span><span class="sxs-lookup"><span data-stu-id="812a9-106">For more information about folder security, see [Secure Folders](security/secure-folders.md).</span></span>  
  
 <span data-ttu-id="812a9-107">Специальные папки, например «Корневая папка», «Мои отчеты» и «Папки пользователей», нельзя переименовывать или перемещать в пространстве имен сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="812a9-107">Special-purpose folders such as Home, My Reports, and Users folders cannot be renamed or moved within the report server namespace.</span></span> <span data-ttu-id="812a9-108">Для этих папок страница «Общие свойства» недоступна.</span><span class="sxs-lookup"><span data-stu-id="812a9-108">The General properties page is not available for these folders.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="812a9-109">Навигация</span><span class="sxs-lookup"><span data-stu-id="812a9-109">Navigation</span></span>  
 <span data-ttu-id="812a9-110">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="812a9-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-general-properties-page-for-a-folder"></a><span data-ttu-id="812a9-111">Открытие страницы свойств папки «Общие»</span><span class="sxs-lookup"><span data-stu-id="812a9-111">To open the General properties page for a folder</span></span>  
  
1.  <span data-ttu-id="812a9-112">Откройте диспетчер отчетов и откройте папку, для которой необходимо просмотреть или настроить свойства.</span><span class="sxs-lookup"><span data-stu-id="812a9-112">Open Report Manager, and open the folder for which you want to view or configure properties.</span></span>  
  
2.  <span data-ttu-id="812a9-113">Под баннером папки на панели инструментов нажмите **Настройки папки**.</span><span class="sxs-lookup"><span data-stu-id="812a9-113">Under the folder banner, in the toolbar, click **Folder Settings**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="812a9-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="812a9-114">Options</span></span>  
 <span data-ttu-id="812a9-115">**имя**;</span><span class="sxs-lookup"><span data-stu-id="812a9-115">**Name**</span></span>  
 <span data-ttu-id="812a9-116">Задайте имя для папки.</span><span class="sxs-lookup"><span data-stu-id="812a9-116">Specify a name for the folder.</span></span> <span data-ttu-id="812a9-117">Имя должно содержать хотя бы одну букву или цифру.</span><span class="sxs-lookup"><span data-stu-id="812a9-117">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="812a9-118">В него могут также входить пробелы и другие символы.</span><span class="sxs-lookup"><span data-stu-id="812a9-118">It can also include spaces and some symbols.</span></span> <span data-ttu-id="812a9-119">Не используйте символы ; ?</span><span class="sxs-lookup"><span data-stu-id="812a9-119">Do not use the characters ; ?</span></span> <span data-ttu-id="812a9-120">: \@ & = +, $ \* \< > | "или/при указании имени.</span><span class="sxs-lookup"><span data-stu-id="812a9-120">: \@ & = + , $ \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="812a9-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="812a9-121">**Description**</span></span>  
 <span data-ttu-id="812a9-122">Введите описание содержимого папки.</span><span class="sxs-lookup"><span data-stu-id="812a9-122">Type a description of the folder contents.</span></span> <span data-ttu-id="812a9-123">Описание представлено на странице «Содержимое» для тех пользователей, которые имеют разрешения на доступ к папке.</span><span class="sxs-lookup"><span data-stu-id="812a9-123">This description appears on the Contents page for users who have permission to access the folder.</span></span>  
  
 <span data-ttu-id="812a9-124">**Скрыть при отображении в виде списка**</span><span class="sxs-lookup"><span data-stu-id="812a9-124">**Hide in list view**</span></span>  
 <span data-ttu-id="812a9-125">Выберите этот параметр, чтобы скрыть папку от пользователей, которые работают в диспетчере отчетов в режиме списка.</span><span class="sxs-lookup"><span data-stu-id="812a9-125">Select this option to hide the folder from users who are using list view mode in Report Manager.</span></span> <span data-ttu-id="812a9-126">Режим списка — формат представления по умолчанию при обзоре иерархии папок сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="812a9-126">List view mode is the default view format when browsing the report server folder hierarchy.</span></span> <span data-ttu-id="812a9-127">В этом режиме имена элементов и описания выводятся на странице в виде списка.</span><span class="sxs-lookup"><span data-stu-id="812a9-127">In list view, item names and descriptions flow across the page.</span></span> <span data-ttu-id="812a9-128">Альтернативный формат — представление в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="812a9-128">The alternate format is details view.</span></span> <span data-ttu-id="812a9-129">В этом формате описания не выводятся, но отображаются другие сведения об элементе.</span><span class="sxs-lookup"><span data-stu-id="812a9-129">Details view omits descriptions, but includes other information about the item.</span></span> <span data-ttu-id="812a9-130">Элементы можно скрывать в формате списка, но нельзя скрывать в формате таблицы.</span><span class="sxs-lookup"><span data-stu-id="812a9-130">Although you can hide an item in list view, you cannot hide an item in details view.</span></span> <span data-ttu-id="812a9-131">Чтобы ограничить доступ к элементу, необходимо создать назначение ролей.</span><span class="sxs-lookup"><span data-stu-id="812a9-131">If you want to restrict access to an item, you must create a role assignment.</span></span>  
  
 <span data-ttu-id="812a9-132">**Применить**</span><span class="sxs-lookup"><span data-stu-id="812a9-132">**Apply**</span></span>  
 <span data-ttu-id="812a9-133">Щелкните, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="812a9-133">Click to save your changes.</span></span>  
  
 <span data-ttu-id="812a9-134">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="812a9-134">**Delete**</span></span>  
 <span data-ttu-id="812a9-135">Нажмите, чтобы удалить папку и ее содержимое.</span><span class="sxs-lookup"><span data-stu-id="812a9-135">Click to remove the folder and its contents.</span></span>  
  
 <span data-ttu-id="812a9-136">**Перемещение**</span><span class="sxs-lookup"><span data-stu-id="812a9-136">**Move**</span></span>  
 <span data-ttu-id="812a9-137">Нажмите, чтобы переместить отчет или папку в пространстве имен сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="812a9-137">Click to relocate a report or folder within the report server namespace.</span></span> <span data-ttu-id="812a9-138">При нажатии этой кнопки открывается страница «Переместить элементы», на которой можно просматривать папки для поиска нового местоположения папки.</span><span class="sxs-lookup"><span data-stu-id="812a9-138">Clicking this button opens the Move Items page that allows you to browse folders for a new folder location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="812a9-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="812a9-139">See Also</span></span>  
 <span data-ttu-id="812a9-140">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="812a9-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="812a9-141">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="812a9-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
