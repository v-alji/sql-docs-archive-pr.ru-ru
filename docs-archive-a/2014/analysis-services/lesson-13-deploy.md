---
title: Занятие 14. Развертывание | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 24863a8a-9017-415a-a97b-fbac76ed0675
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1a55960a0c33a386d978f3c15e489ed7bd861ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654548"
---
# <a name="lesson-14-deploy"></a><span data-ttu-id="be15a-102">Урок 14. Развертывание</span><span class="sxs-lookup"><span data-stu-id="be15a-102">Lesson 14: Deploy</span></span>
  <span data-ttu-id="be15a-103">На этом занятии мы выполним настройку свойства развертывания, указав экземпляр сервера развертывания служб Analysis Services в табличном режиме и имя развертываемой модели.</span><span class="sxs-lookup"><span data-stu-id="be15a-103">In this lesson, you will configure deployment properties; specifying a deployment server instance of Analysis Services running in Tabular mode, and a name for the model you deploy.</span></span> <span data-ttu-id="be15a-104">Затем мы выполним развертывание модели на указанном экземпляре.</span><span class="sxs-lookup"><span data-stu-id="be15a-104">You will then deploy the model to that instance.</span></span> <span data-ttu-id="be15a-105">После развертывания пользователи смогут подключаться к модели с помощью клиентского приложения создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="be15a-105">After it is deployed, users can connect to the model by using a reporting client application.</span></span> <span data-ttu-id="be15a-106">Дополнительные сведения см. в разделе [Развертывание решений табличной модели (табличные службы SSAS)](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="be15a-106">To learn more, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="be15a-107">Предполагаемое время выполнения этого занятия: **5 минут**.</span><span class="sxs-lookup"><span data-stu-id="be15a-107">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="be15a-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="be15a-108">Prerequisites</span></span>  
 <span data-ttu-id="be15a-109">Этот раздел входит в учебник по табличному моделированию, который следует изучать в предложенном порядке.</span><span class="sxs-lookup"><span data-stu-id="be15a-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="be15a-110">Прежде чем выполнять задания в этом занятии, необходимо завершить предыдущее [Занятие 13. Анализ в Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="be15a-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
## <a name="deploy-the-model"></a><span data-ttu-id="be15a-111">Развертывание модели</span><span class="sxs-lookup"><span data-stu-id="be15a-111">Deploy the Model</span></span>  
  
#### <a name="to-configure-deployment-properties"></a><span data-ttu-id="be15a-112">Настройка свойств развертывания</span><span class="sxs-lookup"><span data-stu-id="be15a-112">To configure deployment properties</span></span>  
  
1.  <span data-ttu-id="be15a-113">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]в **обозревателе решений**щелкните правой кнопкой мыши проект **Табличная модель интернет-продаж Adventure Works** и выберите в контекстном меню пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="be15a-113">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click on the **Adventure Works Internet Sales Tabular Model** project, and then in the context menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="be15a-114">В диалоговом окне **Страницы свойств табличной модели интернет-продаж AW** на вкладке **Сервер развертывания**в свойстве **Сервер** введите имя экземпляра служб Analysis Services, запущенном в табличном режиме.</span><span class="sxs-lookup"><span data-stu-id="be15a-114">In the **AW Internet Sales Tabular Model Property Pages** dialog box, under **Deployment Server**, in the **Server** property, type the name of an Analysis Services instance running in Tabular mode.</span></span> <span data-ttu-id="be15a-115">Это будет экземпляр, на котором будет развернута модель.</span><span class="sxs-lookup"><span data-stu-id="be15a-115">This will be the instance your model will be deployed to.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="be15a-116">Для развертывания модели необходимо разрешение администратора на удаленном экземпляре служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="be15a-116">You must have Administrator permissions on a remote Analysis Services instance in-order to deploy to it.</span></span>  
  
3.  <span data-ttu-id="be15a-117">Убедитесь, что для свойства **режим запроса** задано значение **в памяти**.</span><span class="sxs-lookup"><span data-stu-id="be15a-117">Verify the **Query Mode** property is set to **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="be15a-118">Модель, созданная с помощью этого учебника, не будет поддерживаться в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="be15a-118">The model created by using this tutorial is not supported in DirectQuery mode.</span></span>  
  
4.  <span data-ttu-id="be15a-119">В свойстве **базы данных** введите `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="be15a-119">In the **Database** property, type `Adventure Works Internet Sales Model`.</span></span>  
  
5.  <span data-ttu-id="be15a-120">В свойстве имя **куба** введите `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="be15a-120">In the **Cube** Name property, type `Adventure Works Internet Sales Model`.</span></span>  
  
6.  <span data-ttu-id="be15a-121">Проверьте выбранные параметры и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="be15a-121">Verify your selections and then click **OK**.</span></span>  
  
#### <a name="to-deploy-the-adventure-works-internet-sales-tabular-model"></a><span data-ttu-id="be15a-122">Развертывание табличной модели интернет-продаж Adventure Works</span><span class="sxs-lookup"><span data-stu-id="be15a-122">To deploy the Adventure Works Internet Sales tabular model</span></span>  
  
1.  <span data-ttu-id="be15a-123">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]щелкните меню **Сборка** и выберите команду **Развернуть табличную модель интернет-продаж AW**.</span><span class="sxs-lookup"><span data-stu-id="be15a-123">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Build** menu, and then click **Deploy AW Internet Sales Tabular Model**.</span></span>  
  
     <span data-ttu-id="be15a-124">Появится диалоговое окно «Развертывание», в котором будет отображено состояние развертывания метаданных, а также каждая таблица, включенная в модель.</span><span class="sxs-lookup"><span data-stu-id="be15a-124">The Deploy dialog box appears and displays the deployment status of the metadata as well as each table included in the model.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="be15a-125">Заключение</span><span class="sxs-lookup"><span data-stu-id="be15a-125">Conclusion</span></span>  
 <span data-ttu-id="be15a-126">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="be15a-126">Congratulations!</span></span> <span data-ttu-id="be15a-127">На этом заканчивается создание и развертывание табличной модели служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="be15a-127">You are finished authoring and deploying your first Analysis Services tabular model.</span></span> <span data-ttu-id="be15a-128">Этот учебник помог вам выполнить одну из самых распространенных задач в создании табличной модели.</span><span class="sxs-lookup"><span data-stu-id="be15a-128">This tutorial has helped guide you through completing the most common tasks in creating a tabular model.</span></span> <span data-ttu-id="be15a-129">Теперь, когда модель интернет-продаж Adventure Works развернута, можно использовать среду SQL Server Management Studio для управления ею, создания скриптов обработки и плана резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="be15a-129">Now that your Adventure Works Internet Sales Model is deployed, you can use SQL Server Management Studio to manage the model; create process scripts and a backup plan.</span></span> <span data-ttu-id="be15a-130">Пользователи могут подключаться к модели с помощью клиентского приложения для создания отчетов, например Microsoft Excel или [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be15a-130">Users can connect to the model using a reporting client application such as Microsoft Excel or [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)].</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="be15a-131">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="be15a-131">Additional Resources</span></span>  
 <span data-ttu-id="be15a-132">Дополнительные сведения о свойствах табличной модели, поддерживающих отчеты [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)], см. в разделе [Свойства отчетов Power View (табличные службы SSAS)](tabular-models/properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="be15a-132">To learn more about tabular model properties that support [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)] reports, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](tabular-models/properties-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be15a-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="be15a-133">See Also</span></span>  
 <span data-ttu-id="be15a-134">[Режим DirectQuery &#40;табличные&#41;SSAS](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="be15a-134">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 <span data-ttu-id="be15a-135">[Настройка моделирования данных по умолчанию и свойств развертывания &#40;табличных&#41;SSAS](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="be15a-135">[Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="be15a-136">Базы данных табличной модели (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="be15a-136">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-models/tabular-model-databases-ssas-tabular.md)  
  
  
