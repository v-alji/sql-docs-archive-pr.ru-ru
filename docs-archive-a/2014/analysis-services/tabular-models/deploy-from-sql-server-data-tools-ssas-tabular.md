---
title: Развертывание из SQL Server Data Tools (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.deploystatus.f1
ms.assetid: 67dde3fe-ba43-41f3-b56c-c656029ee93f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8bc8008e7c79e1652b54b21e6afb116301d1700b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665138"
---
# <a name="deploy-from-sql-server-data-tools-ssas-tabular"></a><span data-ttu-id="8e13a-102">Развертывание из SQL Server Data Tools (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="8e13a-102">Deploy From SQL Server Data Tools (SSAS Tabular)</span></span>
  <span data-ttu-id="8e13a-103">Задания в этом разделе помогут развернуть решение табличной модели с помощью команды Deploy в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e13a-103">Use the tasks in this topic to deploy a tabular model solution by using the Deploy command in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="8e13a-104">Разделы данной темы:</span><span class="sxs-lookup"><span data-stu-id="8e13a-104">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="8e13a-105">Настройка параметров развертывания и свойств сервера развертывания</span><span class="sxs-lookup"><span data-stu-id="8e13a-105">Configure Deployment Options and Deployment Server Properties</span></span>](#bkmk_deploy)  
  
-   [<span data-ttu-id="8e13a-106">Развертывание решения табличной модели</span><span class="sxs-lookup"><span data-stu-id="8e13a-106">Deploy a Tabular Model Solution</span></span>](#bkmk_deploy_proc)  
  
-   [<span data-ttu-id="8e13a-107">Состояние развертывания</span><span class="sxs-lookup"><span data-stu-id="8e13a-107">Deploy Status</span></span>](#bkmk_deploy_status)  
  
##  <a name="configure-deployment-options-and-deployment-server-properties"></a><a name="bkmk_deploy"></a><span data-ttu-id="8e13a-108">Настройка параметров развертывания и свойств сервера развертывания</span><span class="sxs-lookup"><span data-stu-id="8e13a-108">Configure Deployment Options and Deployment Server Properties</span></span>  
 <span data-ttu-id="8e13a-109">Перед развертыванием решения табличной модели прежде всего необходимо указать параметры развертывания и свойства сервера развертывания.</span><span class="sxs-lookup"><span data-stu-id="8e13a-109">Before you deploy your tabular model solution, you must first specify the Deployment Options and Deployment Server properties.</span></span> <span data-ttu-id="8e13a-110">Дополнительные сведения о настройке свойств и параметров развертывания см. в разделе [Развертывание решений табличной модели (табличные службы SSAS)](tabular-model-solution-deployment-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="8e13a-110">For more information about deployment properties and settings, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
#### <a name="to-configure-deployment-options-and-deployment-server-properties"></a><span data-ttu-id="8e13a-111">Настройка параметров свойств «Параметры развертывания» и «Сервер развертывания»</span><span class="sxs-lookup"><span data-stu-id="8e13a-111">To configure Deployment Options and Deployment Server properties</span></span>  
  
1.  <span data-ttu-id="8e13a-112">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]в **обозревателе решений**щелкните правой кнопкой мыши имя проекта и выберите пункт меню **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8e13a-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click the project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="8e13a-113">В диалоговом окне \*\* \<project name> свойства\*\* в **параметрах развертывания**укажите параметры свойств, если они отличаются от параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8e13a-113">In the **\<project name> Properties** dialog, in **Deployment Options**, specify property settings if different from the default settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8e13a-114">Для моделей в режиме кэширования **Режим запроса** всегда **В памяти**.</span><span class="sxs-lookup"><span data-stu-id="8e13a-114">For models in cached mode, **Query Mode** is always **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8e13a-115">**Параметры олицетворения** нельзя задать для моделей в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="8e13a-115">You cannot specify **Impersonation Settings** for models in DirectQuery mode.</span></span>  
  
3.  <span data-ttu-id="8e13a-116">В области **Сервер развертывания**укажите значения свойств **Сервер** (имя), **Выпуск**, **База данных** (имя) и **Имя куба** , если они отличаются от заданных по умолчанию, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8e13a-116">In **Deployment Server**, specify the **Server** (name), **Edition**, **Database** (name), and **Cube Name** property settings, if different from the default settings, and then click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e13a-117">Можно также указать параметр свойства сервера развертывания по умолчанию, чтобы все создаваемые проекты были автоматически развернуты на указанном сервере.</span><span class="sxs-lookup"><span data-stu-id="8e13a-117">You can also specify the Default Deployment Server property setting so any new projects you create will automatically be deployed to the specified server.</span></span> <span data-ttu-id="8e13a-118">Дополнительные сведения см. в разделе [Настройка моделирования данных по умолчанию и свойств развертывания (табличные службы SSAS)](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="8e13a-118">For more information, see [Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
##  <a name="deploy-a-tabular-model-solution"></a><a name="bkmk_deploy_proc"></a><span data-ttu-id="8e13a-119">Развертывание решения табличной модели</span><span class="sxs-lookup"><span data-stu-id="8e13a-119">Deploy a Tabular Model Solution</span></span>  
  
#### <a name="to-deploy-a-tabular-model-solution"></a><span data-ttu-id="8e13a-120">Развертывание решения табличной модели</span><span class="sxs-lookup"><span data-stu-id="8e13a-120">To deploy a tabular model solution</span></span>  
  
-   <span data-ttu-id="8e13a-121">В в [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] меню **Сборка** выберите пункт \*\*Развернуть \<project name> \*\*.</span><span class="sxs-lookup"><span data-stu-id="8e13a-121">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **Build** menu, click **Deploy \<project name>**.</span></span>  
  
     <span data-ttu-id="8e13a-122">Появится диалоговое окно **Развертывание** , в котором будет отображаться состояние развертывания метаданных и обработки каждой таблицы (если для свойства "Вариант обработки" не выбрано значение "Не обрабатывать"), включенной в модель.</span><span class="sxs-lookup"><span data-stu-id="8e13a-122">The **Deploy** dialog box will appear and indicate the status of the metadata deployment and the processing (unless Processing Option property is set to Do Not Process) of each table included in the model.</span></span> <span data-ttu-id="8e13a-123">После завершения процесса развертывания с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] подключитесь к экземпляру служб Analysis Services и проверьте, был ли создан новый объект шаблона базы данных, либо используйте клиентское приложение создания отчетов для подключения к развернутой модели.</span><span class="sxs-lookup"><span data-stu-id="8e13a-123">After the deployment process is complete, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to connect to the Analysis Services instance and verify the new model database object has been created or use a client reporting application to connect to the deployed model.</span></span>  
  
##  <a name="deploy-status"></a><a name="bkmk_deploy_status"></a> <span data-ttu-id="8e13a-124">Состояние развертывания</span><span class="sxs-lookup"><span data-stu-id="8e13a-124">Deploy Status</span></span>  
 <span data-ttu-id="8e13a-125">Диалоговое окно **Развертывание** позволяет отслеживать ход выполнения операций развертывания.</span><span class="sxs-lookup"><span data-stu-id="8e13a-125">The **Deploy** dialog box enables you to monitor the progress of a Deploy operation.</span></span> <span data-ttu-id="8e13a-126">Операцию развертывания также можно остановить.</span><span class="sxs-lookup"><span data-stu-id="8e13a-126">A deploy operation can also be stopped.</span></span>  
  
 <span data-ttu-id="8e13a-127">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="8e13a-127">**Status**</span></span>  
 <span data-ttu-id="8e13a-128">Сообщает об успешности операции развертывания.</span><span class="sxs-lookup"><span data-stu-id="8e13a-128">Indicates whether the Deploy operation was successful or not.</span></span>  
  
 <span data-ttu-id="8e13a-129">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="8e13a-129">**Details**</span></span>  
 <span data-ttu-id="8e13a-130">Перечисляет развернутые элементы метаданных, состояние для каждого элемента метаданных и выдает сообщения о любых неполадках.</span><span class="sxs-lookup"><span data-stu-id="8e13a-130">Lists the metadata items that were deployed, the status for each metadata item, and provides a message of any issues.</span></span>  
  
 <span data-ttu-id="8e13a-131">**Остановить развертывание**</span><span class="sxs-lookup"><span data-stu-id="8e13a-131">**Stop Deploy**</span></span>  
 <span data-ttu-id="8e13a-132">Щелкните, чтобы остановить операцию развертывания.</span><span class="sxs-lookup"><span data-stu-id="8e13a-132">Click to halt the Deploy operation.</span></span> <span data-ttu-id="8e13a-133">Этот параметр полезен, если операция развертывания занимает слишком много времени либо обнаружено слишком много ошибок.</span><span class="sxs-lookup"><span data-stu-id="8e13a-133">This option is useful if the Deploy operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e13a-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e13a-134">See Also</span></span>  
 <span data-ttu-id="8e13a-135">[Развертывание решения табличной модели &#40;табличные&#41;SSAS](tabular-model-solution-deployment-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="8e13a-135">[Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="8e13a-136">Настройка моделирования данных по умолчанию и свойств развертывания (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="8e13a-136">Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
