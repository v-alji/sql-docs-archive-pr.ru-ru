---
title: Описание XML настраиваемого рабочего процесса (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e267e5f4-38bb-466d-82e8-871eabeec07e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77906426ddb901ec422367bf30aabef2e532ad06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669443"
---
# <a name="custom-workflow-xml-description-master-data-services"></a><span data-ttu-id="f7f44-102">Описание XML настраиваемого рабочего процесса (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f7f44-102">Custom Workflow XML Description (Master Data Services)</span></span>
  <span data-ttu-id="f7f44-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] метод [Microsoft. MasterDataServices. Воркфловтипикстендер. Иворкфловтипикстендер. стартворкфлов \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) вызывается службой интеграции рабочего процесса MDS SQL Server при запуске рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f7f44-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)], the [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) method is called by SQL Server MDS Workflow Integration Service when a workflow starts.</span></span> <span data-ttu-id="f7f44-104">Этот метод получает метаданные и данные об элементе, вызвавшем срабатывание бизнес-правила рабочего процесса, в виде блока XML-данных.</span><span class="sxs-lookup"><span data-stu-id="f7f44-104">This method receives metadata and data about the item that triggered the workflow business rule as a block of XML.</span></span> <span data-ttu-id="f7f44-105">Пример кода, который реализует обработчик рабочего процесса, см. в разделе [Пример пользовательского рабочего процесса (службы Master Data Services)](create-a-custom-workflow-example.md).</span><span class="sxs-lookup"><span data-stu-id="f7f44-105">For example code that implements a workflow handler, see [Custom Workflow Example &#40;Master Data Services&#41;](create-a-custom-workflow-example.md).</span></span>  
  
 <span data-ttu-id="f7f44-106">В следующем примере показано, как могут выглядеть XML-данные, которые отправляются обработчику рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f7f44-106">The following example shows what the XML that is sent to the workflow handler might look like:</span></span>  
  
```scr  
<ExternalAction>  
  <Type>TEST</Type>  
  <SendData>1</SendData>  
  <Server_URL>This is my test!</Server_URL>  
  <Action_ID>Test Workflow</Action_ID>  
  <Model_ID>5</Model_ID>  
  <Model_Name>Customer</Model_Name>  
  <Entity_ID>34</Entity_ID>  
  <Entity_Name>Customer</Entity_Name>  
  <Version_ID>8</Version_ID>  
  <MemberType_ID>1</MemberType_ID>  
  <Member_ID>12</Member_ID>  
  <MemberData>  
    <ID>12</ID>  
    <Version_ID>8</Version_ID>  
    <ValidationStatus_ID>3</ValidationStatus_ID>  
    <ChangeTrackingMask>0</ChangeTrackingMask>  
    <EnterDTM>2011-02-25T20:16:36.650</EnterDTM>  
    <EnterUserID>2</EnterUserID>  
    <EnterUserName>MyUserName</EnterUserName>  
    <EnterUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</EnterUserMuid>  
    <EnterVersionId>8</EnterVersionId>  
    <EnterVersionName>VERSION_1</EnterVersionName>  
    <EnterVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</EnterVersionMuid>  
    <LastChgDTM>2011-02-25T20:16:36.650</LastChgDTM>  
    <LastChgUserID>2</LastChgUserID>  
    <LastChgUserName>MyUserName</LastChgUserName>  
    <LastChgUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</LastChgUserMuid>  
    <LastChgVersionId>8</LastChgVersionId>  
    <LastChgVersionName>VERSION_1</LastChgVersionName>  
    <LastChgVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</LastChgVersionMuid>  
    <Name>Test Customer</Name>  
    <Code>TC</Code>  
  </MemberData>  
</ExternalAction>  
```  
  
 <span data-ttu-id="f7f44-107">В следующей таблице описаны некоторые теги, которые содержатся в этих XML-данных.</span><span class="sxs-lookup"><span data-stu-id="f7f44-107">The following table describes some of the tags contained in this XML:</span></span>  
  
|<span data-ttu-id="f7f44-108">Тег</span><span class="sxs-lookup"><span data-stu-id="f7f44-108">Tag</span></span>|<span data-ttu-id="f7f44-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f7f44-109">Description</span></span>|  
|---------|-----------------|  
|\<Type>|<span data-ttu-id="f7f44-110">Текст, введенный в поле **Тип рабочего процесса** в [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], указывает пользовательскую сборку рабочего процесса, которая будет загружаться.</span><span class="sxs-lookup"><span data-stu-id="f7f44-110">The text you entered in the **Workflow type** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] to identify which custom workflow assembly to load.</span></span>|  
|\<SendData>|<span data-ttu-id="f7f44-111">Логическое значение, которое в [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] управляется флажком **Включить в сообщение данные элементов**.</span><span class="sxs-lookup"><span data-stu-id="f7f44-111">A Boolean value controlled by the **Include member data in the message** checkbox in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="f7f44-112">Значение 1 означает, что \<MemberData> раздел отправляется; в противном случае \<MemberData> раздел не отправляется.</span><span class="sxs-lookup"><span data-stu-id="f7f44-112">A value of 1 means that the \<MemberData> section is sent; otherwise the \<MemberData> section is not sent.</span></span>|  
|<span data-ttu-id="f7f44-113"><Server_URL></span><span class="sxs-lookup"><span data-stu-id="f7f44-113"><Server_URL></span></span>|<span data-ttu-id="f7f44-114">Текст, введенный в поле **Сайт рабочего процесса** в [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7f44-114">The text you entered in the **Workflow site** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|<span data-ttu-id="f7f44-115"><Action_ID></span><span class="sxs-lookup"><span data-stu-id="f7f44-115"><Action_ID></span></span>|<span data-ttu-id="f7f44-116">Текст, введенный в поле **Имя рабочего процесса** в [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7f44-116">The text you entered in the **Workflow name** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|\<MemberData>|<span data-ttu-id="f7f44-117">Содержит данные элемента, вызвавшего срабатывание действия рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f7f44-117">Contains the data of the member that triggered the workflow action.</span></span> <span data-ttu-id="f7f44-118">Он включается, только если значение \<SendData> равно 1.</span><span class="sxs-lookup"><span data-stu-id="f7f44-118">This is included only if the value of \<SendData> is 1.</span></span>|  
|\<Enter*xxx*>|<span data-ttu-id="f7f44-119">Этот набор тегов содержит метаданные о создании элемента, например дату создания и автора.</span><span class="sxs-lookup"><span data-stu-id="f7f44-119">This set of tags contains metadata about the creation of the member, such as when it was created and who created it.</span></span>|  
|\<LastChg*xxx*>|<span data-ttu-id="f7f44-120">Этот набор тегов содержит метаданные о последнем изменении, внесенном в элемент, например дату внесения изменения и автора.</span><span class="sxs-lookup"><span data-stu-id="f7f44-120">This set of tags contains metadata about the last change made to the member, such as when the change was made and who made it.</span></span>|  
|\<Name>|<span data-ttu-id="f7f44-121">Первый атрибут элемента, который был изменен.</span><span class="sxs-lookup"><span data-stu-id="f7f44-121">The first attribute of the member that was changed.</span></span> <span data-ttu-id="f7f44-122">Этот пример элемента содержит только атрибуты Name и Code.</span><span class="sxs-lookup"><span data-stu-id="f7f44-122">This example member contains only Name and Code attributes.</span></span>|  
|\<Code>|<span data-ttu-id="f7f44-123">Следующий атрибут элемента, который был изменен.</span><span class="sxs-lookup"><span data-stu-id="f7f44-123">The next attribute of the member that was changed.</span></span> <span data-ttu-id="f7f44-124">Если бы этот пример элемента содержал больше атрибутов, то они следовали бы за первым.</span><span class="sxs-lookup"><span data-stu-id="f7f44-124">If this example member contained more attributes, they would follow this one.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7f44-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="f7f44-125">See Also</span></span>  
 <span data-ttu-id="f7f44-126">[Создание настраиваемого &#40;рабочего процесса Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f7f44-126">[Create a Custom Workflow &#40;Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span></span>  
 [<span data-ttu-id="f7f44-127">Пример настраиваемого рабочего процесса (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f7f44-127">Custom Workflow Example &#40;Master Data Services&#41;</span></span>](create-a-custom-workflow-example.md)  
  
  
