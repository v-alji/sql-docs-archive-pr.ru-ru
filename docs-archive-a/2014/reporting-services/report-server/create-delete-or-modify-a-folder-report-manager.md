---
title: Создание, изменение или удаление папки (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing folders
- modifying folders
- deleting folders
- folders [Reporting Services], creating
- folders [Reporting Services], deleting
- folders [Reporting Services], modifying
ms.assetid: d62159a8-ec67-4e28-a9f1-05a9250065bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bd7d5ceebdb7b3a48ded66ed108bddda25d8a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665804"
---
# <a name="create-delete-or-modify-a-folder-report-manager"></a><span data-ttu-id="48d27-102">создать, изменить или удалить папку (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="48d27-102">Create, Delete, or Modify a Folder (Report Manager)</span></span>
  <span data-ttu-id="48d27-103">Для упорядочения элементов и управления элементами, публикуемыми на сервере отчетов, можно создать папки.</span><span class="sxs-lookup"><span data-stu-id="48d27-103">You can create folders to organize and manage the items you publish to a report server.</span></span> <span data-ttu-id="48d27-104">Создание папок поможет пользователям находить интересующие их отчеты.</span><span class="sxs-lookup"><span data-stu-id="48d27-104">Creating folders can help users find reports of interest to them.</span></span> <span data-ttu-id="48d27-105">Для диспетчеров содержимого папки обеспечивают инфраструктуру для применения разрешений.</span><span class="sxs-lookup"><span data-stu-id="48d27-105">For content managers, folders provide a framework for applying permissions.</span></span> <span data-ttu-id="48d27-106">Можно создать назначения ролей для определенных папок, чтобы ограничить доступ к отчетам, которые находятся на стадии разработки или не подлежат широкому распространению.</span><span class="sxs-lookup"><span data-stu-id="48d27-106">You can create role assignments on specific folders to restrict access to reports that are in development or that should not be widely distributed.</span></span>  
  
### <a name="to-create-a-folder"></a><span data-ttu-id="48d27-107">Создание папки</span><span class="sxs-lookup"><span data-stu-id="48d27-107">To create a folder</span></span>  
  
1.  <span data-ttu-id="48d27-108">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="48d27-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="48d27-109">В диспетчере отчетов выберите корневую папку, а затем нажмите **Создать папку**.</span><span class="sxs-lookup"><span data-stu-id="48d27-109">In Report Manager, select the Home folder and click **New Folder**.</span></span> <span data-ttu-id="48d27-110">Либо, чтобы создать папку внутри существующей папки, перейдите к этой папке на странице **Содержимое** , а затем щелкните папку, чтобы открыть ее.</span><span class="sxs-lookup"><span data-stu-id="48d27-110">Or, to create a folder under an existing folder, navigate to that folder in the **Contents** page and click the folder to open it.</span></span> <span data-ttu-id="48d27-111">После этого нажмите **Создать папку**.</span><span class="sxs-lookup"><span data-stu-id="48d27-111">Then click **New Folder**.</span></span>  
  
     <span data-ttu-id="48d27-112">Откроется страница **Создание папки** .</span><span class="sxs-lookup"><span data-stu-id="48d27-112">The **New Folder** page opens.</span></span>  
  
3.  <span data-ttu-id="48d27-113">Введите имя папки.</span><span class="sxs-lookup"><span data-stu-id="48d27-113">Type a folder name.</span></span> <span data-ttu-id="48d27-114">Имя папки может включать пробелы, но не может содержать зарезервированные символы, используемые для кодирования URL-адреса: ; ?</span><span class="sxs-lookup"><span data-stu-id="48d27-114">A folder name can include spaces, but cannot include reserved characters that are used for URL encoding: ; ?</span></span> <span data-ttu-id="48d27-115">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="48d27-115">: \@ & = + , $ / \* \< > |.</span></span> <span data-ttu-id="48d27-116">Нельзя указать последовательность имен папок, чтобы одновременно создать несколько папок.</span><span class="sxs-lookup"><span data-stu-id="48d27-116">You cannot type a series of folder names to create several folders at once.</span></span>  
  
4.  <span data-ttu-id="48d27-117">При необходимости введите также описание.</span><span class="sxs-lookup"><span data-stu-id="48d27-117">Optionally type a description.</span></span>  
  
5.  <span data-ttu-id="48d27-118">Выберите пункт **Скрыть при отображении в виде списка** , если папка не должна отображаться в представлении по умолчанию страницы **Содержимое** .</span><span class="sxs-lookup"><span data-stu-id="48d27-118">Select **Hide in list view** if you do not want to display the folder in the default view of the **Contents** page.</span></span> <span data-ttu-id="48d27-119">Она будет видна пользователям только после нажатия кнопки **Показать подробности** на странице **Содержимое** .</span><span class="sxs-lookup"><span data-stu-id="48d27-119">The folder will be visible to users only when they click **Show Details** on the **Contents** page.</span></span>  
  
6.  <span data-ttu-id="48d27-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="48d27-120">Click **OK**.</span></span>  
  
### <a name="to-delete-a-folder"></a><span data-ttu-id="48d27-121">Удаление папки</span><span class="sxs-lookup"><span data-stu-id="48d27-121">To delete a folder</span></span>  
  
1.  <span data-ttu-id="48d27-122">Перейдите в диспетчере отчетов на страницу **Содержимое** и найдите элемент, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="48d27-122">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="48d27-123">Подведите курсор к элементу и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="48d27-123">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="48d27-124">В раскрывающемся меню выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="48d27-124">In the drop-down menu, click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-modify-or-delete-a-folder"></a><span data-ttu-id="48d27-125">Удаление или изменение папки</span><span class="sxs-lookup"><span data-stu-id="48d27-125">To modify or delete a folder</span></span>  
  
1.  <span data-ttu-id="48d27-126">Перейдите в диспетчере отчетов на страницу **Содержимое** и найдите элемент, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="48d27-126">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="48d27-127">Подведите курсор к элементу и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="48d27-127">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="48d27-128">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="48d27-128">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="48d27-129">Откроется страница «Общие свойства».</span><span class="sxs-lookup"><span data-stu-id="48d27-129">The General Properties page opens.</span></span>  
  
4.  <span data-ttu-id="48d27-130">Для изменения местоположения папки нажмите кнопку **Переместить**.</span><span class="sxs-lookup"><span data-stu-id="48d27-130">To change the folder location, click **Move**.</span></span> <span data-ttu-id="48d27-131">Введите путь к целевой папке или выберите место назначения в дереве папок, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="48d27-131">Type the location of the destination folder, or choose the destination folder from the tree, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="48d27-132">Или измените свойства папки одним из приведенных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="48d27-132">Or, modify folder properties in the following ways:</span></span>  
  
    -   <span data-ttu-id="48d27-133">Чтобы изменить отображаемые сведения о папке, введите имя или описание.</span><span class="sxs-lookup"><span data-stu-id="48d27-133">To modify display text about the folder, type a name or description.</span></span>  
  
    -   <span data-ttu-id="48d27-134">Чтобы папка отображалась в представлении по умолчанию страницы **Содержимое** , сбросьте флажок **Скрывать при просмотре списка**.</span><span class="sxs-lookup"><span data-stu-id="48d27-134">To display the folder in the default view on the **Contents** page, clear **Hide in list view**.</span></span>  
  
6.  <span data-ttu-id="48d27-135">Или, если нужно удалить папку вместе с ее содержимым, нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="48d27-135">Or, to remove the folder and its contents, click **Delete**.</span></span>  
  
7.  <span data-ttu-id="48d27-136">Щелкните **Применить**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="48d27-136">Click **Apply** to save changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d27-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="48d27-137">See Also</span></span>  
 <span data-ttu-id="48d27-138">[Страница "Создание папки" &#40;диспетчер отчетов&#41;](../new-folder-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="48d27-138">[New Folder Page &#40;Report Manager&#41;](../new-folder-page-report-manager.md) </span></span>  
 <span data-ttu-id="48d27-139">[Страница "содержимое" &#40;диспетчер отчетов&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="48d27-139">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 [<span data-ttu-id="48d27-140">Поиск, просмотр отчетов и управление ими (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="48d27-140">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
