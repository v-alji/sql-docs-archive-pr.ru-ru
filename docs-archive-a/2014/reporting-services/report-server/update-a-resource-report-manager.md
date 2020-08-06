---
title: Обновление ресурса (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- updating resources
- resources [Reporting Services], updating
ms.assetid: d21f7493-bcf7-4e9e-9886-55ebdc1f1037
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0fca59e476c2820b715ff46729784edc562f74d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659330"
---
# <a name="update-a-resource-report-manager"></a><span data-ttu-id="dfaa6-102">обновить ресурс (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="dfaa6-102">Update a Resource (Report Manager)</span></span>
  <span data-ttu-id="dfaa6-103">Ресурс можно обновить, заменив его более новой версией.</span><span class="sxs-lookup"><span data-stu-id="dfaa6-103">You can update a resource by replacing it with a newer version.</span></span> <span data-ttu-id="dfaa6-104">Ресурсы представляют собой хранящиеся на сервере отчетов элементы, по содержимому аналогичные переданным файлам.</span><span class="sxs-lookup"><span data-stu-id="dfaa6-104">Resources are items stored on a report server that contain content from a file that you upload.</span></span> <span data-ttu-id="dfaa6-105">Можно заменить существующий ресурс, импортировав в существующий ресурс обновленное или совершенно другое содержимое файла.</span><span class="sxs-lookup"><span data-stu-id="dfaa6-105">You can replace an existing resource by importing new or different file content into the existing resource.</span></span> <span data-ttu-id="dfaa6-106">Обновление ресурса позволяет заменить только содержимое ресурса, сохраняя его существующие свойства и настройки безопасности.</span><span class="sxs-lookup"><span data-stu-id="dfaa6-106">Updating a resource provides a way to update content while preserving existing properties and security settings on the resource.</span></span>  
  
### <a name="to-update-a-resource"></a><span data-ttu-id="dfaa6-107">Обновление ресурса</span><span class="sxs-lookup"><span data-stu-id="dfaa6-107">To update a resource</span></span>  
  
1.  <span data-ttu-id="dfaa6-108">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="dfaa6-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="dfaa6-109">В диспетчере отчетов перейдите к ресурсу, который нужно обновить, или найдите его.</span><span class="sxs-lookup"><span data-stu-id="dfaa6-109">In Report Manager, navigate to or search for the resource you want to update.</span></span>  
  
3.  <span data-ttu-id="dfaa6-110">Щелкните ресурс, чтобы открыть его на странице **Вид** .</span><span class="sxs-lookup"><span data-stu-id="dfaa6-110">Click the resource to open it in the **View** page.</span></span>  
  
4.  <span data-ttu-id="dfaa6-111">Нажмите кнопку **Свойства** , чтобы открыть страницу свойств **Общие** .</span><span class="sxs-lookup"><span data-stu-id="dfaa6-111">Click **Properties** to open the **General** properties page.</span></span>  
  
5.  <span data-ttu-id="dfaa6-112">Нажмите кнопку **Заменить** , чтобы открыть страницу **Импорт ресурса** .</span><span class="sxs-lookup"><span data-stu-id="dfaa6-112">Click **Replace** to open the **Import Resource** page.</span></span>  
  
6.  <span data-ttu-id="dfaa6-113">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="dfaa6-113">Click **Browse**.</span></span>  
  
7.  <span data-ttu-id="dfaa6-114">Выберите файл, которым нужно заменить содержимое текущего ресурса.</span><span class="sxs-lookup"><span data-stu-id="dfaa6-114">Select the file that you want to use to replace the current resource.</span></span> <span data-ttu-id="dfaa6-115">Можно использовать обновленную версию файла или указать файл, имеющий другое имя или тип.</span><span class="sxs-lookup"><span data-stu-id="dfaa6-115">You can use an updated version of the resource file, or specify a file with a different name or file type.</span></span>  
  
8.  <span data-ttu-id="dfaa6-116">Нажмите кнопку **ОК** , чтобы передать файл ресурса, закройте страницу **Импорт ресурса** и сохраните произведенные изменения на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="dfaa6-116">Click **OK** to upload the resource file, close the **Import Resource** page, and save your changes to the report server.</span></span>  
  
 <span data-ttu-id="dfaa6-117">Если обновляемый ресурс содержит изображение, используемое в отчете, необходимо обновить отчет, чтобы изображение в нем обновилось.</span><span class="sxs-lookup"><span data-stu-id="dfaa6-117">If the resource you are updating contains an image that is used in a report, you need to refresh the report to see the updated image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfaa6-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="dfaa6-118">See Also</span></span>  
 <span data-ttu-id="dfaa6-119">[Страница "содержимое" &#40;диспетчер отчетов&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dfaa6-119">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="dfaa6-120">[Страница "Отправка файла" &#40;диспетчер отчетов&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dfaa6-120">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 <span data-ttu-id="dfaa6-121">[Отправка файлов в папку](upload-files-to-a-folder.md) </span><span class="sxs-lookup"><span data-stu-id="dfaa6-121">[Upload Files to a Folder](upload-files-to-a-folder.md) </span></span>  
 [<span data-ttu-id="dfaa6-122">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="dfaa6-122">Report Manager F1 Help</span></span>](../report-manager-f1-help.md)  
  
  
