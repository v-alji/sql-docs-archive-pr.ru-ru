---
title: Удалить модель интеллектуального анализа данных из структуры интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], mining models
- deleting mining models
- removing mining models
- mining models [Analysis Services], deleting
ms.assetid: 9ab1506b-856e-4762-a663-5adf15ac71e3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72c79dcdccf6225b8e75144f8b090dcab7506c10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667487"
---
# <a name="delete-a-mining-model-from-a-mining-structure"></a><span data-ttu-id="005c8-102">удалить модель интеллектуального анализа данных из структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="005c8-102">Delete a Mining Model from a Mining Structure</span></span>
  <span data-ttu-id="005c8-103">Модели интеллектуального анализа данных можно удалять в конструкторе интеллектуального анализа данных с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]или инструкций расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="005c8-103">You can delete mining models by using Data Mining Designer, by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or by using DMX statements.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="005c8-104">Удаление модели интеллектуального анализа данных с помощью SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="005c8-104">Delete a mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="005c8-105">Перейдите на вкладку **Модели интеллектуального анализа данных** в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="005c8-105">Select the **Mining Models** tab in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="005c8-106">Щелкните правой кнопкой мыши модель, которую необходимо удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="005c8-106">Right-click the model that you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="005c8-107">Откроется диалоговое окно **Удаление объектов** .</span><span class="sxs-lookup"><span data-stu-id="005c8-107">The **Delete Objects** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="005c8-108">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="005c8-108">Click **OK**.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-management-studio"></a><span data-ttu-id="005c8-109">Удаление модели интеллектуального анализа данных с помощью среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="005c8-109">Delete a mining model using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="005c8-110">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте базу данных [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , содержащую модель.</span><span class="sxs-lookup"><span data-stu-id="005c8-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains the model.</span></span>  
  
2.  <span data-ttu-id="005c8-111">Разверните **Структуры интеллектуального анализа данных**, затем **Модели интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="005c8-111">Expand **Mining Structures**, and then expand **Mining Models**.</span></span>  
  
3.  <span data-ttu-id="005c8-112">Щелкните правой кнопкой мыши модель, которую необходимо удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="005c8-112">Right-click the model you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="005c8-113">Удаление модели не приводит к удалению обучающих данных. Удаляются только метаданные и шаблоны, созданные при обучении модели.</span><span class="sxs-lookup"><span data-stu-id="005c8-113">Deleting the model does not delete the training data, only the metadata and any patterns created when you trained the model.</span></span>  
  
### <a name="delete-a-mining-model-using-dmx"></a><span data-ttu-id="005c8-114">Удаление модели интеллектуального анализа данных с помощью расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="005c8-114">Delete a mining model using DMX</span></span>  
  
-   [<span data-ttu-id="005c8-115">DROP MINING MODEL (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="005c8-115">DROP MINING MODEL &#40;DMX&#41;</span></span>](/sql/dmx/drop-mining-model-dmx)  
  
## <a name="see-also"></a><span data-ttu-id="005c8-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="005c8-116">See Also</span></span>  
 [<span data-ttu-id="005c8-117">Задачи и инструкции по модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="005c8-117">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
