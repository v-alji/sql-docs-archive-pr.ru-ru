---
title: Публикация и повторная публикация элементов отчетов (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92dce484-f39b-403c-9caf-d8772bc3aca3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95fd5e3f7519c6a0d4a6f08cb9bcbf2507d32aaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658096"
---
# <a name="publish-and-republish-report-parts-report-builder-and-ssrs"></a><span data-ttu-id="ea7f7-102">Публикация и повторная публикация элементов отчетов (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="ea7f7-102">Publish and Republish Report Parts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ea7f7-103">Предусмотрена возможность публикации элемента отчета с настройками по умолчанию в заданном по умолчанию местоположении или изменения таких метаданных элемента отчета, как заголовок и описание, с последующим сохранением где-то в другом месте на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-103">You can publish a report part with default settings in a default location, or you can edit report part metadata such as name and description, and save it somewhere else on a report server.</span></span> <span data-ttu-id="ea7f7-104">Можно также сохранить ее на сайте SharePoint, который объединен с сервером отчетов (при наличии соответствующих разрешений).</span><span class="sxs-lookup"><span data-stu-id="ea7f7-104">You can also save it to a SharePoint site that is integrated with a report server if you have the correct permissions.</span></span>  
  
 <span data-ttu-id="ea7f7-105">Можно опубликовать только элемент отчета с внедренным в него набором данных, от которого он зависит, или опубликовать набор данных отдельно.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-105">You can publish just the report part, with the dataset that it depends on embedded in it, or you can publish the dataset separately.</span></span> <span data-ttu-id="ea7f7-106">Если набор данных публикуется отдельно, он становится общим набором данных, и элемент отчета ссылается на него.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-106">If you publish the dataset separately, it becomes a shared dataset, and the report part links to it.</span></span> <span data-ttu-id="ea7f7-107">Дополнительные сведения см. в разделе [Элементы отчета и наборы данных в построителе отчетов](../report-data/report-parts-and-datasets-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="ea7f7-107">For more information, see [Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="ea7f7-108">Можно повторно опубликовать существующий элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-108">You can republish an existing report part.</span></span> <span data-ttu-id="ea7f7-109">При наличии разрешений пользователь может сохранить элемент отчета на сервере, перезаписав исходный экземпляр, даже если он его не создавал.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-109">If you have permissions, you can save over the original instance of the report part on the server, even if you didn't create it.</span></span> <span data-ttu-id="ea7f7-110">Можно также опубликовать его как новый элемент отчета и сохранить в том же или в другом расположении.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-110">You can also publish it as a new report part and save it either in the same or a different location.</span></span>  
  
### <a name="to-publish-a-report-part"></a><span data-ttu-id="ea7f7-111">Публикация элемента отчета</span><span class="sxs-lookup"><span data-stu-id="ea7f7-111">To publish a report part</span></span>  
  
1.  <span data-ttu-id="ea7f7-112">В меню построителя отчетов выберите команду **Публикации элементов отчетов**.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-112">On the Report Builder menu, click **Publish Report Parts**.</span></span>  
  
     <span data-ttu-id="ea7f7-113">Если пользователь не подключен к серверу отчетов, то получит приглашение подключиться.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-113">If you are not connected to a report server, you will be prompted to connect.</span></span> <span data-ttu-id="ea7f7-114">Если пользователь не сможет подключиться к серверу отчетов, то не будет иметь возможности публиковать элементы отчетов.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-114">If you cannot connect to a report server, you cannot publish report parts.</span></span>  
  
2.  <span data-ttu-id="ea7f7-115">Чтобы сохранить элемент отчета с настройками по умолчанию в заданном по умолчанию местоположении, нажмите **Опубликовать все элементы отчетов с настройками по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-115">To save your report parts with default settings to the default location, click **Publish all report parts with default settings**.</span></span>  
  
     <span data-ttu-id="ea7f7-116">В противном случае нажмите **Просмотреть и изменить элементы отчетов перед публикацией**.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-116">Otherwise, click **Review and modify report parts before publishing**.</span></span>  
  
3.  <span data-ttu-id="ea7f7-117">Измените имя и описание элемента отчета: дважды щелкните имя, чтобы изменить его, и щелкните поле **Описание** , чтобы добавить описание.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-117">Edit the report part name and description: Double-click the name to edit it and click in the **Description** field to add a description.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea7f7-118">Рекомендуется присваивать элементу отчета имя и описание, чтобы было проще идентифицировать ее при поиске.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-118">It is a good idea to give the report part name and description, to help people identify it when searching.</span></span> <span data-ttu-id="ea7f7-119">Максимальная длина имени элемента отчета составляет 260 символов для всего пути, включая имена папок на сервере, за которым следует фактическое имя элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-119">The maximum length for the name of a report part is 260 characters for the entire path, including the names of the folders on the server, followed by the actual name of the report part.</span></span>  
  
4.  <span data-ttu-id="ea7f7-120">Чтобы сохранить конкретный элемент отчета в папке, отличной от применяемой по умолчанию, нажмите кнопку **Обзор** .</span><span class="sxs-lookup"><span data-stu-id="ea7f7-120">To save your report part to a folder other than the default, click the **Browse** button.</span></span>  
  
5.  <span data-ttu-id="ea7f7-121">После задания параметров для всех элементов отчета в отчете нажмите **Публиковать**.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-121">When you have set the options for all the report parts in the report, click **Publish**.</span></span>  
  
     <span data-ttu-id="ea7f7-122">После публикации элементов отчетов в диалоговом окне будет показано, какие элементы отчетов опубликованы успешно, а какие нет.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-122">After you publish the report parts, the dialog box shows which were successfully published and which were not.</span></span> <span data-ttu-id="ea7f7-123">Можно ознакомиться с дополнительными сведениями об элементах отчетов, которые не удалось опубликовать, в диалоговом окне **Публикации элементов отчетов** .</span><span class="sxs-lookup"><span data-stu-id="ea7f7-123">You can view details in the **Publish Report Parts** dialog box for the report parts that failed to publish.</span></span>  
  
6.  <span data-ttu-id="ea7f7-124">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-124">Click **Close**.</span></span>  
  
### <a name="to-republish-a-report-part"></a><span data-ttu-id="ea7f7-125">Переиздание элемента отчета</span><span class="sxs-lookup"><span data-stu-id="ea7f7-125">To republish a report part</span></span>  
  
1.  <span data-ttu-id="ea7f7-126">Следуйте приведенной выше процедуре, чтобы опубликовать элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-126">Follow the previous procedure for publishing a report part.</span></span>  
  
2.  <span data-ttu-id="ea7f7-127">Если в диалоговом окне **Публикации элементов отчетов** нажать **Опубликовать как новую копию элемента отчета**, то построитель отчетов не будет сохранять элемент отчета, перезаписывая существующий на сервере, а создаст вместо этого другой элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-127">In the **Publish Report Parts** dialog box, if you click **Publish as a New Copy of the Report Part**, Report Builder will not save over the existing report part on the server, but will create another report part instead.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea7f7-128">Если элемент отчета будет опубликован как новый, то получит новый уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-128">If you publish it as a new report part, it will have a new unique ID.</span></span> <span data-ttu-id="ea7f7-129">Она больше не будет получать обновления при изменении исходного элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="ea7f7-129">It will no longer receive updates if the original report part changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea7f7-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea7f7-130">See Also</span></span>  
 <span data-ttu-id="ea7f7-131">[Элементы отчета &#40;построитель отчетов и службы SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ea7f7-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ea7f7-132">[Элементы отчета и наборы данных в построитель отчетов](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="ea7f7-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="ea7f7-133">[Устранение неполадок элементов отчетов &#40;построитель отчетов и SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ea7f7-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ea7f7-134">[Проверка наличия обновлений или отключение обновлений &#40;построитель отчетов и служб SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ea7f7-134">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ea7f7-135">Просмотр элементов отчета и назначение папки по умолчанию (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="ea7f7-135">Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;</span></span>](browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md)  
  
  
