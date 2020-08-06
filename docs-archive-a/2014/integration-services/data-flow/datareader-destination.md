---
title: Назначение DataReader | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.datareaderdest.f1
helpviewer_keywords:
- DataReader destination
- destinations [Integration Services], DataReader
ms.assetid: 56fcc4bf-c901-42c3-a71d-110039293431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 40cfe5d99c33eb19d415f204173005a64bde7855
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751360"
---
# <a name="datareader-destination"></a><span data-ttu-id="4337d-102">назначение DataReader</span><span class="sxs-lookup"><span data-stu-id="4337d-102">DataReader Destination</span></span>
  <span data-ttu-id="4337d-103">Назначение DataReader извлекает данные из потока данных с помощью интерфейса ADO.NET `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="4337d-103">The DataReader destination exposes the data in a data flow by using the ADO.NET `DataReader` interface.</span></span> <span data-ttu-id="4337d-104">Эти данные могут быть впоследствии использованы другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="4337d-104">The data can then be consumed by other applications.</span></span> <span data-ttu-id="4337d-105">Например, можно настроить источник данных из отчета служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] на использование результата выполнения пакета служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4337d-105">For example, you can configure the data source of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report to use the result of running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="4337d-106">Для этого нужно создать поток данных, который реализует назначение DataReader.</span><span class="sxs-lookup"><span data-stu-id="4337d-106">To do this, you create a data flow that implements the DataReader destination.</span></span>  
  
 <span data-ttu-id="4337d-107">Дополнительные сведения о доступе и чтении значений в назначении DataReader программным способом см. в разделе [Загрузка выхода локального пакета](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span><span class="sxs-lookup"><span data-stu-id="4337d-107">For information about accessing and reading values in the DataReader destination programmatically, see [Loading the Output of a Local Package](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span></span>  
  
## <a name="configuration-of-the-datareader-destination"></a><span data-ttu-id="4337d-108">Настройка назначения «DataReader»</span><span class="sxs-lookup"><span data-stu-id="4337d-108">Configuration of the DataReader Destination</span></span>  
 <span data-ttu-id="4337d-109">Можно указать значение времени ожидания для назначения DataReader и установить, должно ли назначение завершиться неудачей по истечении времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="4337d-109">You can specify a time-out value for the DataReader destination and indicate whether the destination should fail if a time-out occurs.</span></span> <span data-ttu-id="4337d-110">Время ожидания истекает, если приложение не требует данных в течение заданного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="4337d-110">A time-out occurs if the application does not ask for data within the specified time.</span></span>  
  
 <span data-ttu-id="4337d-111">Назначение DataReader имеет один вход.</span><span class="sxs-lookup"><span data-stu-id="4337d-111">The DataReader destination has one input.</span></span> <span data-ttu-id="4337d-112">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4337d-112">It does not support an error output.</span></span>  
  
 <span data-ttu-id="4337d-113">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="4337d-113">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4337d-114">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="4337d-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="4337d-115">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="4337d-115">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="4337d-116">Пользовательские свойства назначения «Модуль чтения данных»</span><span class="sxs-lookup"><span data-stu-id="4337d-116">DataReader Destination Custom Properties</span></span>](datareader-destination-custom-properties.md)  
  
 <span data-ttu-id="4337d-117">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="4337d-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
