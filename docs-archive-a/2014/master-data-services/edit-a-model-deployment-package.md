---
title: Изменение пакета развертывания модели | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6b0fdb7d-83dd-4392-9011-4ae642c471f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b8bfd7083e2ba763d15a405266260b5a096c8378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669433"
---
# <a name="edit-a-model-deployment-package"></a><span data-ttu-id="538e4-102">Изменение пакета развертывания модели</span><span class="sxs-lookup"><span data-stu-id="538e4-102">Edit a Model Deployment Package</span></span>
  <span data-ttu-id="538e4-103">В этом разделе описывается развертывание в MDS выбранных частей модели вместо всей модели.</span><span class="sxs-lookup"><span data-stu-id="538e4-103">This topic describes how to deploy selected parts of a model in MDS, rather than an entire model.</span></span> <span data-ttu-id="538e4-104">Для этого пакет модели MDS необходимо изменить в редакторе пакетов моделей.</span><span class="sxs-lookup"><span data-stu-id="538e4-104">To do so, you edit an MDS model package using the Model Package Editor.</span></span>  
  
 <span data-ttu-id="538e4-105">Мастер редактора пакетов моделей позволяет выбирать в модели отдельные сущности, производные иерархии, представления подписок и бизнес-правила, которые будут включены в пакет MDS и впоследствии развернуты.</span><span class="sxs-lookup"><span data-stu-id="538e4-105">The Model Package Editor wizard enables you to select the specific entities, derived hierarchies, subscription views, and business rules in a model that you want to include in an MDS package, and then later deploy.</span></span> <span data-ttu-id="538e4-106">Части модели, развертывать которые не требуется, вы можете оставить невыбранными.</span><span class="sxs-lookup"><span data-stu-id="538e4-106">You can leave out those parts of the model that you do not want to deploy.</span></span> <span data-ttu-id="538e4-107">При выборе сущности также автоматически выбираются все зависимые объекты в этой сущности.</span><span class="sxs-lookup"><span data-stu-id="538e4-107">When you select an entity, all of the dependent objects in that entity are also automatically selected.</span></span>  
  
 <span data-ttu-id="538e4-108">С помощью редактора пакетов моделей можно выбирать части модели в файле пакета, созданном либо средством MDSModelDeploy (оно создает файл пакета, включающий объекты и данные), либо мастером развертывания моделей (он создает файл, включающий только структуру модели).</span><span class="sxs-lookup"><span data-stu-id="538e4-108">You use the Model Package Editor to select parts of a model in a package file that was created by either the MDSModelDeploy tool (which creates a package file that includes objects and data) or the Model Deployment wizard (which creates a file that includes only the model structure).</span></span> <span data-ttu-id="538e4-109">После редактирования модели в пакете используйте средство MDSModelDeploy для развертывания объектов и данных или мастер развертывания моделей для развертывания лишь структуры модели.</span><span class="sxs-lookup"><span data-stu-id="538e4-109">After editing the model in the package, you use the MDSModelDeploy tool to deploy objects and data, or the Model Deployment wizard to deploy just the model structure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="538e4-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="538e4-110">Prerequisites</span></span>  
 <span data-ttu-id="538e4-111">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="538e4-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="538e4-112">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="538e4-112">You must be a model administrator.</span></span> <span data-ttu-id="538e4-113">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="538e4-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="538e4-114">Должен существовать пакет модели для изменения.</span><span class="sxs-lookup"><span data-stu-id="538e4-114">A model package must exist for you to edit.</span></span> <span data-ttu-id="538e4-115">Дополнительные сведения см. в разделах [Развертывание моделей (службы Master Data Services)](../../2014/master-data-services/deploying-models-master-data-services.md) и [Создание пакета развертывания модели с помощью мастера](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) или [Создание пакета развертывания модели при помощи MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="538e4-115">For more information, see [Deploying Models &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md) and [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) or [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
### <a name="to-edit-a-model-deployment-package"></a><span data-ttu-id="538e4-116">Изменения пакета развертывания модели</span><span class="sxs-lookup"><span data-stu-id="538e4-116">To edit a model deployment package</span></span>  
  
1.  <span data-ttu-id="538e4-117">В проводнике Windows на сервере MDS перейдите в папку *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="538e4-117">In Windows Explorer on the MDS server, move to *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
2.  <span data-ttu-id="538e4-118">Запустите ModelPackageEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="538e4-118">Execute ModelPackageEditor.exe.</span></span>  
  
3.  <span data-ttu-id="538e4-119">В мастере редактора пакетов моделей нажмите кнопку **Обзор**, перейдите к папке, в которой содержатся пакеты, выберите пакет и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="538e4-119">In the Model Package Editor wizard, click **Browse**, move to the folder containing your packages, select a package, and then click **Open**.</span></span> <span data-ttu-id="538e4-120">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="538e4-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="538e4-121">Выберите сущности, производные иерархии, представления подписок или бизнес-правила, которые необходимо развернуть.</span><span class="sxs-lookup"><span data-stu-id="538e4-121">Select those entities, derived hierarchies, subscriptions views, or business rules that you want to deploy.</span></span> <span data-ttu-id="538e4-122">Снимите выбор тех из них, которые не требуется развертывать.</span><span class="sxs-lookup"><span data-stu-id="538e4-122">Deselect those that you do not want to deploy.</span></span> <span data-ttu-id="538e4-123">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="538e4-123">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="538e4-124">Проверьте список выбранных объектов для развертывания.</span><span class="sxs-lookup"><span data-stu-id="538e4-124">Verify the list of selections to deploy.</span></span> <span data-ttu-id="538e4-125">Чтобы изменить его, нажмите кнопку **Назад** и повторите шаг 4.</span><span class="sxs-lookup"><span data-stu-id="538e4-125">To change, click **Back** and repeat step 4.</span></span>  
  
6.  <span data-ttu-id="538e4-126">Нажмите кнопку **Обзор**, перейдите к папке, в которой следует сохранить частичный пакет, и введите имя файла частичного пакета (с расширением .pkg).</span><span class="sxs-lookup"><span data-stu-id="538e4-126">Click **Browse**, move to the folder that you want to save the partial package in, and then enter the file name of the partial package (with a .pkg extension).</span></span> <span data-ttu-id="538e4-127">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="538e4-127">Click **Save**.</span></span>  
  
7.  <span data-ttu-id="538e4-128">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="538e4-128">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="538e4-129">Next Steps</span><span class="sxs-lookup"><span data-stu-id="538e4-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="538e4-130">Развертывание пакета развертывания модели с помощью мастера</span><span class="sxs-lookup"><span data-stu-id="538e4-130">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
-   [<span data-ttu-id="538e4-131">Развертывание пакета развертывания модели при помощи MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="538e4-131">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
  
