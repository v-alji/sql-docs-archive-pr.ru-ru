---
title: Создание пакета развертывания модели с помощью мастера | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], creating
- models [Master Data Services], creating a deployment package
- creating packages [Master Data Services]
ms.assetid: b24ec4c2-1378-4c72-ac69-4ec2647030f0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: abb30f9d8e08d8eec8e04960b61575da3a1dbcc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668408"
---
# <a name="create-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="cf5c5-102">Создание пакета развертывания модели с помощью мастера</span><span class="sxs-lookup"><span data-stu-id="cf5c5-102">Create a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="cf5c5-103">Мастер развертывания модели [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] служит для создания пакета, содержащего только объекты модели.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to create a package of the model objects only.</span></span> <span data-ttu-id="cf5c5-104">Если в пакет нужно включить данные, см. раздел [Создание пакета развертывания модели при помощи MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="cf5c5-104">If you need to include data in the package, see [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cf5c5-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="cf5c5-105">Prerequisites</span></span>  
 <span data-ttu-id="cf5c5-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="cf5c5-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="cf5c5-107">В веб-приложении [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="cf5c5-107">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="cf5c5-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-108">You must be a model administrator.</span></span> <span data-ttu-id="cf5c5-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cf5c5-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="cf5c5-110">Для создания пакета модели модель должна существовать.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-110">A model must exist for you to create a package of.</span></span> <span data-ttu-id="cf5c5-111">Дополнительные сведения см. в разделе [Создание модели (службы Master Data Services)](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cf5c5-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package"></a><span data-ttu-id="cf5c5-112">Создание пакета развертывания модели</span><span class="sxs-lookup"><span data-stu-id="cf5c5-112">To create a model deployment package</span></span>  
  
1.  <span data-ttu-id="cf5c5-113">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="cf5c5-114">На странице **Представление модели** в строке меню наведите курсор на пункт **Система** и выберите **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-114">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="cf5c5-115">В **Мастере развертывания модели**выберите команду **Создать**.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-115">On the **Model Deployment Wizard**, click **Create**.</span></span>  
  
4.  <span data-ttu-id="cf5c5-116">На странице **Создание пакета** выберите модель в списке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="cf5c5-116">On the **Create Package** page, select a model from the **Model** list.</span></span>  
  
5.  <span data-ttu-id="cf5c5-117">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-117">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="cf5c5-118">Щелкните элемент **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-118">Click **Download**.</span></span>  
  
7.  <span data-ttu-id="cf5c5-119">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-119">Save the file.</span></span>  
  
8.  <span data-ttu-id="cf5c5-120">Нажмите кнопку **Закрыть**, чтобы завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-120">Click **Close** to close the wizard.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cf5c5-121">Next Steps</span><span class="sxs-lookup"><span data-stu-id="cf5c5-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="cf5c5-122">Развертывание пакета развертывания модели с помощью мастера</span><span class="sxs-lookup"><span data-stu-id="cf5c5-122">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="cf5c5-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf5c5-123">See Also</span></span>  
 [<span data-ttu-id="cf5c5-124">Развертывание моделей (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="cf5c5-124">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
