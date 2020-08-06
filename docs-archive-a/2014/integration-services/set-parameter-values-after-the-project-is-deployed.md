---
title: Установка значений параметров после развертывания проекта | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c9dcca4d-f1a0-45ec-b078-f4d372589baf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39572594e429b61de0641c6e6929e84105138f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751291"
---
# <a name="set-parameter-values-after-the-project-is-deployed"></a><span data-ttu-id="bb192-102">Задать значения параметров после развертывания проекта</span><span class="sxs-lookup"><span data-stu-id="bb192-102">Set Parameter Values After the Project Is Deployed</span></span>
  <span data-ttu-id="bb192-103">Мастер развертывания позволяет задавать значения параметров по умолчанию сервера при развертывании проекта в каталог.</span><span class="sxs-lookup"><span data-stu-id="bb192-103">The Deployment Wizard allows you to set server default parameter values when you deploy your project to the catalog.</span></span> <span data-ttu-id="bb192-104">После развертывания проекта в каталог задать значения по умолчанию сервера можно будет с помощью обозревателя объектов среды SQL Server Management Studio (SSMS) или Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="bb192-104">After your project is in the catalog, you can use SQL Server Management Studio (SSMS) Object Explorer or Transact-SQL to set server default values.</span></span>  
  
### <a name="to-set-server-defaults-with-ssms-object-explorer"></a><span data-ttu-id="bb192-105">Установка параметры по умолчанию сервера с помощью обозревателя объектов SSMS</span><span class="sxs-lookup"><span data-stu-id="bb192-105">To set server defaults with SSMS Object Explorer:</span></span>  
  
1.  <span data-ttu-id="bb192-106">Выберите и щелкните правой кнопкой мыши проект в узле **Службы Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="bb192-106">Select and right-click the project under the **Integration Services** node.</span></span>  
  
2.  <span data-ttu-id="bb192-107">Выберите пункт **Свойства** , чтобы открыть диалоговое окно **Свойства проекта** .</span><span class="sxs-lookup"><span data-stu-id="bb192-107">Click **Properties** to open the **Project Properties** dialog window.</span></span>  
  
3.  <span data-ttu-id="bb192-108">Откройте страницу «Параметры», нажав кнопку **Параметры** в разделе **Выбор страницы**.</span><span class="sxs-lookup"><span data-stu-id="bb192-108">Open the parameters page by clicking **Parameters** under **Select a page**.</span></span>  
  
4.  <span data-ttu-id="bb192-109">Выберите нужный параметр в списке **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="bb192-109">Select the desired parameter in the **Parameters** list.</span></span> <span data-ttu-id="bb192-110">Примечание. Столбец **Контейнер** помогает отличить параметры проекта от параметров пакета.</span><span class="sxs-lookup"><span data-stu-id="bb192-110">Note: The **Container** column helps distinguish project parameters from package parameters.</span></span>  
  
5.  <span data-ttu-id="bb192-111">В столбце **Значение** укажите необходимое значение параметра по умолчанию сервера.</span><span class="sxs-lookup"><span data-stu-id="bb192-111">In the **Value** column, specify the desired server default parameter value.</span></span>  
  
 <span data-ttu-id="bb192-112">Чтобы установить параметры по умолчанию сервера с использованием Transact-SQL, используйте хранимую процедуру [catalog.set_object_parameter_value (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="bb192-112">To set server defaults with Transact-SQL, use the [catalog.set_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database) stored procedure.</span></span> <span data-ttu-id="bb192-113">Для просмотра текущих значений по умолчанию сервера используйте запрос к представлению [catalog.object_parameters (база данных SSISDB)](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="bb192-113">To view current server defaults, query the [catalog.object_parameters &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database) view.</span></span> <span data-ttu-id="bb192-114">Чтобы удалить значение по умолчанию сервера, используйте хранимую процедуру, используйте хранимую процедуру [catalog.clear_object_parameter_value (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="bb192-114">To clear a server default value, use the [catalog.clear_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database) stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb192-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb192-115">See Also</span></span>  
 [<span data-ttu-id="bb192-116">Integration Services параметры &#40;служб SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="bb192-116">Integration Services &#40;SSIS&#41; Parameters</span></span>](integration-services-ssis-package-and-project-parameters.md)  
  
  
