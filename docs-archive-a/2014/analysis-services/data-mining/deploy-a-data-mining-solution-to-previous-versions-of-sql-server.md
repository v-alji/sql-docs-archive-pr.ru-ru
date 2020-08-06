---
title: Развертывание решения интеллектуального анализа данных в предыдущих версиях SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- backward compatibility [Analysis Services]
- holdout [data mining]
- deploy [Analysis Services]
- time series [Analysis Services]
- deploying [Analysis Services - data mining]
- synchronization [Analysis Services]
- deployment [Analysis Services]
ms.assetid: 2715c245-f206-43af-8bf5-e6bd2585477a
author: minewiskan
ms.author: owend
ms.openlocfilehash: f09a37c078cf58f24db9a08e3ddcb68cb2638717
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667485"
---
# <a name="deploy-a-data-mining-solution-to-previous-versions-of-sql-server"></a><span data-ttu-id="767b4-102">Развертывание решения интеллектуального анализа данных в предыдущих версиях SQL Server</span><span class="sxs-lookup"><span data-stu-id="767b4-102">Deploy a Data Mining Solution to Previous Versions of SQL Server</span></span>
  <span data-ttu-id="767b4-103">В этом разделе описаны известные проблемы совместимости, которые могут возникнуть во время развертывания модели или структуры интеллектуального анализа данных, созданной в экземпляре служб [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] , в базе данных со службами SQL Server 2005 Analysis Services, а также при развертывании моделей, созданных в SQL Server 2005, на экземпляре [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="767b4-103">This section describes known compatibility issues that may arise when you attempt to deploy a data mining model or data mining structure that was created in an instance of [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] to a database that uses SQL Server 2005 Analysis Services, or when you deploy models created in SQL Server 2005 to an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="767b4-104">Развертывание на экземпляре служб SQL Server 2000 Analysis Services не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="767b4-104">Deployment to an instance of SQL Server 2000 Analysis Services is not supported.</span></span>  
  
 [<span data-ttu-id="767b4-105">Развертывание моделей временных рядов</span><span class="sxs-lookup"><span data-stu-id="767b4-105">Deploying Time Series Models</span></span>](#bkmk_TimeSeries)  
  
 [<span data-ttu-id="767b4-106">Развертывание моделей с контрольными данными</span><span class="sxs-lookup"><span data-stu-id="767b4-106">Deploying Models with Holdout</span></span>](#bkmk_Holdout)  
  
 [<span data-ttu-id="767b4-107">Развертывание моделей с фильтрами</span><span class="sxs-lookup"><span data-stu-id="767b4-107">Deploying Models with Filters</span></span>](#bkmk_Filter)  
  
 [<span data-ttu-id="767b4-108">Восстановление из резервных копий базы данных</span><span class="sxs-lookup"><span data-stu-id="767b4-108">Restoring from Database Backups</span></span>](#bkmk_Backup)  
  
 [<span data-ttu-id="767b4-109">Использование синхронизации базы данных</span><span class="sxs-lookup"><span data-stu-id="767b4-109">Using Database Synchronization</span></span>](#bkmk_Synch)  
  
##  <a name="deploying-times-series-models"></a><a name="bkmk_TimeSeries"></a><span data-ttu-id="767b4-110">Развертывание моделей временных рядов</span><span class="sxs-lookup"><span data-stu-id="767b4-110">Deploying Times Series Models</span></span>  
 <span data-ttu-id="767b4-111">Алгоритм временных рядов (Майкрософт) в SQL Server 2008 был расширен. В него был добавлен второй, дополнительный алгоритм ARIMA.</span><span class="sxs-lookup"><span data-stu-id="767b4-111">The Microsoft Time Series algorithm was enhanced in SQL Server 2008 by the addition of a second, complementary algorithm, ARIMA.</span></span> <span data-ttu-id="767b4-112">Дополнительные сведения об изменениях в алгоритме временных рядов см. в разделе [Алгоритм временных рядов (Майкрософт)](microsoft-time-series-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="767b4-112">For more information about the changes in the time series algorithm, see [Microsoft Time Series Algorithm](microsoft-time-series-algorithm.md).</span></span>  
  
 <span data-ttu-id="767b4-113">Поэтому модели временных рядов, в которых используется алгоритм ARIMA, при развертывании на экземпляре служб SQL Server 2005 Analysis Services могут работать иначе.</span><span class="sxs-lookup"><span data-stu-id="767b4-113">Therefore, time series mining models that use the new ARIMA algorithm may behave differently when deployed to an instance of SQL Server 2005 Analysis Services.</span></span>  
  
 <span data-ttu-id="767b4-114">Если явно задан параметр PREDICTION_SMOOTHING, управляющий смешиванием моделей ARTXP и ARIMA в процессе прогнозирования, то при развертывании такой модели на экземпляре SQL Server 2005 службы Analysis Services выдадут сообщение об ошибке, указывающее на недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="767b4-114">If you have explicitly set the parameter PREDICTION_SMOOTHING to control the mixture of ARTXP and ARIMA models in prediction, when you deploy this model to an instance of SQL Server 2005, Analysis Services will raise an error stating that the parameter is not valid.</span></span> <span data-ttu-id="767b4-115">Чтобы избежать этой ошибки, удалите параметр PREDICTION_SMOOTHING и преобразуйте модель таким образом, чтобы в ней использовался только алгоритм ARTXP.</span><span class="sxs-lookup"><span data-stu-id="767b4-115">To prevent this error, you must delete the PREDICTION_SMOOTHING parameter and convert the models to a pure ARTXP model.</span></span>  
  
 <span data-ttu-id="767b4-116">И наоборот, если при развертывании модели временных рядов, созданной в службах SQL Server 2005 Analysis Services, в экземпляре [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]открыть модель интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], то файлы определений сначала преобразуются в новый формат, а во все модели временных рядов по умолчанию будут добавлены два новых параметра.</span><span class="sxs-lookup"><span data-stu-id="767b4-116">Conversely, if you deploy a time series model that was created using SQL Server 2005 Analysis Services to an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], when you open the mining model in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the definition files are first converted to the new format, and two new parameters are added by default to all time series models.</span></span> <span data-ttu-id="767b4-117">Параметр FORECAST_METHOD добавляется со значением по умолчанию MIXED, а параметр PREDICTION_SMOOTHING — со значением 0,5.</span><span class="sxs-lookup"><span data-stu-id="767b4-117">The parameter FORECAST_METHOD is added with the default value of MIXED, and the parameter PREDICTION_SMOOTHING is added with the default value of 0.5.</span></span> <span data-ttu-id="767b4-118">Однако до повторной обработки при прогнозировании модель будет по-прежнему использовать только алгоритм ARTXP.</span><span class="sxs-lookup"><span data-stu-id="767b4-118">However, the model will continue to use only ARTXP for forecasting until you reprocess the model.</span></span> <span data-ttu-id="767b4-119">После повторной обработки модели при прогнозировании будет использоваться как алгоритм ARIMA, так и алгоритм ARTXP.</span><span class="sxs-lookup"><span data-stu-id="767b4-119">As soon as you reprocess the model, prediction changes to use both ARIMA and ARTXP.</span></span>  
  
 <span data-ttu-id="767b4-120">Поэтому, если желательно избежать изменения модели, ее следует только просматривать, но не обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="767b4-120">Therefore, if you wish to avoid changing the model, you should only browse the model and never process it.</span></span> <span data-ttu-id="767b4-121">Кроме того, параметры FORECAST_METHOD и PREDICTION_SMOOTHING можно задать явным образом.</span><span class="sxs-lookup"><span data-stu-id="767b4-121">Alternatively, you could explicitly set the FORECAST_METHOD or PREDICTION_SMOOTHING parameters.</span></span>  
  
 <span data-ttu-id="767b4-122">Дополнительные сведения о настройке смешанных моделей см. в разделе [Технический справочник по алгоритму временных рядов (Майкрософт)](microsoft-time-series-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="767b4-122">For detailed information about configuring mixed models, see [Microsoft Time Series Algorithm Technical Reference](microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="767b4-123">Если источник данных обслуживается поставщиком данных клиента SQL 10, то необходимо также изменить определение источника данных, указав предыдущую версию собственного клиента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="767b4-123">If the provider that is used for the model's data source is SQL Client Data Provider 10, you must also modify the data source definition to specify the previous version of the SQL Server Native Client.</span></span> <span data-ttu-id="767b4-124">В противном случае среда [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] создает сообщение об ошибке, извещающее о том, что поставщик не зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="767b4-124">Otherwise, [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] generates an error stating that the provider is not registered.</span></span>  
  
##  <a name="deploying-models-with-holdout"></a><a name="bkmk_Holdout"></a> <span data-ttu-id="767b4-125">Развертывание моделей с контрольными данными</span><span class="sxs-lookup"><span data-stu-id="767b4-125">Deploying Models with Holdout</span></span>  
 <span data-ttu-id="767b4-126">Если созданная в службах [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] структура интеллектуального анализа данных содержит контрольную секцию данных для проверки моделей интеллектуального анализа данных, то такая структура может быть развернута на экземпляре SQL Server 2005, однако сведения о секции будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="767b4-126">If you use [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] to create a mining structure that contains a holdout partition used for testing data mining models, the mining structure can be deployed to an instance of SQL Server 2005, but the partition information will be lost.</span></span>  
  
 <span data-ttu-id="767b4-127">При открытии структуры интеллектуального анализа данных в службах SQL Server 2005 Analysis Services среда [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] выдает ошибку и производит повторное формирование структуры, удаляя контрольную секцию.</span><span class="sxs-lookup"><span data-stu-id="767b4-127">When you open the mining structure in SQL Server 2005 Analysis Services, [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] raises an error, and then regenerates the structure to remove the holdout partition.</span></span>  
  
 <span data-ttu-id="767b4-128">После перестроения структуры размер контрольной секции больше не будет доступен в окно свойств; Однако значение \<ddl100_100:HoldoutMaxPercent> 30 \</ddl100_100:HoldoutMaxPercent> ) по-прежнему может присутствовать в файле скрипта ASSL.</span><span class="sxs-lookup"><span data-stu-id="767b4-128">After the structure has been rebuilt, the size of the holdout partition is no longer available in the Properties window; however, the value \<ddl100_100:HoldoutMaxPercent>30\</ddl100_100:HoldoutMaxPercent>) may still be present in the ASSL script file.</span></span>  
  
##  <a name="deploying-models-with-filters"></a><a name="bkmk_Filter"></a> <span data-ttu-id="767b4-129">Развертывание моделей с фильтрами</span><span class="sxs-lookup"><span data-stu-id="767b4-129">Deploying Models with Filters</span></span>  
 <span data-ttu-id="767b4-130">Если в службах [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] к модели интеллектуального анализа данных применен фильтр, то такая модель может быть развернута на экземпляре SQL Server 2005, но фильтр к ней применен не будет.</span><span class="sxs-lookup"><span data-stu-id="767b4-130">If you use [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] to apply a filter to a mining model, the model can be deployed to an instance of SQL Server 2005, but the filter will not be applied.</span></span>  
  
 <span data-ttu-id="767b4-131">При открытии модели интеллектуального анализа данных среда [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] выдает ошибку и производит повторное формирование модели, чтобы удалить фильтр.</span><span class="sxs-lookup"><span data-stu-id="767b4-131">When you open the mining model, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] raises an error, and then regenerates the model to remove the filter.</span></span>  
  
##  <a name="restoring-from-database-backups"></a><a name="bkmk_Backup"></a><span data-ttu-id="767b4-132">Восстановление из резервных копий базы данных</span><span class="sxs-lookup"><span data-stu-id="767b4-132">Restoring from Database Backups</span></span>  
 <span data-ttu-id="767b4-133">Резервную копию базы данных, созданную в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , нельзя восстановить на экземпляре SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="767b4-133">You cannot restore a database backup that was created in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to an instance of SQL Server 2005.</span></span> <span data-ttu-id="767b4-134">При попытке сделать это среда SQL Server Management Studio сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="767b4-134">If you do so, SQL Server Management Studio generates an error.</span></span>  
  
 <span data-ttu-id="767b4-135">Если создать резервную копию базы данных служб SQL Server 2005 Analysis Services и восстановить ее на экземпляре [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], все модели временных рядов будут изменены, как описано в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="767b4-135">If you create a backup of a SQL Server 2005 Analysis Services database and restore this backup on an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], all time series models are modified as described in the previous section.</span></span>  
  
##  <a name="using-database-synchronization"></a><a name="bkmk_Synch"></a><span data-ttu-id="767b4-136">Использование синхронизации базы данных</span><span class="sxs-lookup"><span data-stu-id="767b4-136">Using Database Synchronization</span></span>  
 <span data-ttu-id="767b4-137">Синхронизация базы данных с [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] на SQL Server 2005 не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="767b4-137">Database synchronization is not supported from [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to SQL Server 2005.</span></span>  
  
 <span data-ttu-id="767b4-138">При попытке синхронизации базы данных [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] сервер вернет ошибку, а синхронизация будет отменена.</span><span class="sxs-lookup"><span data-stu-id="767b4-138">If you attempt to synchronize a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] database, the server returns an error and database synchronization fails.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="767b4-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="767b4-139">See Also</span></span>  
 [<span data-ttu-id="767b4-140">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="767b4-140">Analysis Services Backward Compatibility</span></span>](../analysis-services-backward-compatibility.md)  
  
  
