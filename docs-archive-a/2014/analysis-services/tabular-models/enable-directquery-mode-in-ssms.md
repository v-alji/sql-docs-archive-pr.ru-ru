---
title: Настройка доступа в памяти или DirectQuery для базы данных табличной модели | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5d439a9-5be1-4145-90e8-90777d80e98b
author: minewiskan
ms.author: owend
ms.openlocfilehash: a607bc6c11f35736487932bdf10d239afc8b5355
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728841"
---
# <a name="configure-in-memory-or-directquery-access-for-a-tabular-model-database"></a><span data-ttu-id="4d8cb-102">Настройка доступа в памяти или доступа DirectQuery для базы данных табличной модели</span><span class="sxs-lookup"><span data-stu-id="4d8cb-102">Configure In-Memory or DirectQuery Access for a Tabular Model Database</span></span>
  <span data-ttu-id="4d8cb-103">В этом разделе описано, как изменить свойства подключения уже развернутой табличной модели, чтобы ее можно было использовать в режиме прямого запроса (Direct Query).</span><span class="sxs-lookup"><span data-stu-id="4d8cb-103">This topic describes how to change the connection properties of a tabular model that has already been deployed, to enable use of the model in Direct Query mode.</span></span>  
  
 <span data-ttu-id="4d8cb-104">Дополнительные сведения об этих свойствах и конфигурации для наиболее распространенных сценариев см. в статье [сценарии развертывания DirectQuery &#40;табличных&#41;SSAS ](../directquery-deployment-scenarios-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="4d8cb-104">For more information about these properties, and configuration for the most common scenarios, see [DirectQuery Deployment Scenarios &#40;SSAS Tabular&#41;](../directquery-deployment-scenarios-ssas-tabular.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d8cb-105">Требования</span><span class="sxs-lookup"><span data-stu-id="4d8cb-105">Requirements</span></span>  
 <span data-ttu-id="4d8cb-106">Включение использования режима Direct Query — это многоступенчатый процесс.</span><span class="sxs-lookup"><span data-stu-id="4d8cb-106">Enabling the use of Direct Query mode on a tabular model is a multistep process.</span></span> <span data-ttu-id="4d8cb-107">Необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="4d8cb-107">You must:</span></span>  
  
1.  <span data-ttu-id="4d8cb-108">убедиться в том, что модель не имеет функций, которые могут вызвать ошибки при проверке в режиме Direct Query;</span><span class="sxs-lookup"><span data-stu-id="4d8cb-108">Ensure that the model does not have features which might cause validation errors in Direct Query mode.</span></span>  
  
2.  <span data-ttu-id="4d8cb-109">изменить режим хранения для модели для поддержки режима Direct Query;</span><span class="sxs-lookup"><span data-stu-id="4d8cb-109">Change the storage mode on the model to support Direct Query.</span></span>  
  
3.  <span data-ttu-id="4d8cb-110">развернуть модель в режиме, который поддерживает запросы как в гибридном, так и чистом режиме Direct Query;</span><span class="sxs-lookup"><span data-stu-id="4d8cb-110">Deploy the model in a mode that supports queries in either a hybrid or pure Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="4d8cb-111">изменить строку подключения развернутой базы данных для поддержки режима Direct Query.</span><span class="sxs-lookup"><span data-stu-id="4d8cb-111">Edit the connection string on the deployed database to support Direct Query mode.</span></span>  
  
 <span data-ttu-id="4d8cb-112">Предполагается, что модель уже создана и проверена и требуется только обеспечить доступ в режиме Direct Query с такого клиента, как [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d8cb-112">This topic assumes that you have created and validated your model, and only need to enable Direct Query access from a client such as [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="4d8cb-113">Процедура</span><span class="sxs-lookup"><span data-stu-id="4d8cb-113">Procedure</span></span>  
  
#### <a name="change-the-connection-string-properties-of-the-model"></a><span data-ttu-id="4d8cb-114">Изменение свойств строки подключения для модели</span><span class="sxs-lookup"><span data-stu-id="4d8cb-114">Change the Connection String Properties of the Model</span></span>  
  
1.  <span data-ttu-id="4d8cb-115">В среде SQL Server Management Studio откройте экземпляр, на котором развернута модель.</span><span class="sxs-lookup"><span data-stu-id="4d8cb-115">In SQL Server Management Studio, open the instance to which you deployed the model.</span></span>  
  
2.  <span data-ttu-id="4d8cb-116">В обозревателе объектов щелкните правой кнопкой мыши имя базы данных model и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="4d8cb-116">In Object Explorer, right-click the name of the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="4d8cb-117">Нахождение свойства **DirectQueryMode**.</span><span class="sxs-lookup"><span data-stu-id="4d8cb-117">Locate the property, **DirectQueryMode**.</span></span> <span data-ttu-id="4d8cb-118">Чтобы включить использование реляционного источника данных, это свойство должно иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="4d8cb-118">To enable use of the relational data source, this property must be set to one of these values:</span></span>  
  
    -   <span data-ttu-id="4d8cb-119">**DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="4d8cb-119">**DirectQuery**</span></span>  
  
    -   <span data-ttu-id="4d8cb-120">**InMemoryWithDirectQuery**</span><span class="sxs-lookup"><span data-stu-id="4d8cb-120">**InMemoryWithDirectQuery**</span></span>  
  
    -   <span data-ttu-id="4d8cb-121">**DirectQueryWithInMemory**</span><span class="sxs-lookup"><span data-stu-id="4d8cb-121">**DirectQueryWithInMemory**</span></span>  
  
  
