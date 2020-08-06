---
title: Обработка структуры интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], processing
ms.assetid: 4162f33e-c23f-4293-8905-271781e45fa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d25a927ae61ee5ffadf4ca21073a1c04cdb542
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734614"
---
# <a name="process-a-mining-structure"></a><span data-ttu-id="c8095-102">обработать структуру интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="c8095-102">Process a Mining Structure</span></span>
  <span data-ttu-id="c8095-103">Перед тем как получить возможность просмотра или работы с моделями интеллектуального анализа данных, связанными со структурой интеллектуального анализа данных, необходимо развернуть проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и обработать структуру интеллектуального анализа данных, а также модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="c8095-103">Before you can browse or work with the mining models that are associated with a mining structure, you have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span> <span data-ttu-id="c8095-104">Также при внесении изменений в структуру интеллектуального анализа данных или модель интеллектуального анализа данных будет выдано приглашение к их повторному развертыванию и обработке.</span><span class="sxs-lookup"><span data-stu-id="c8095-104">Also, if you make a change to the mining structure or mining models, you will be prompted to redeploy and process them.</span></span> <span data-ttu-id="c8095-105">При обработке структуры на вкладке **Структура интеллектуального анализа данных** конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] обрабатываются все связанные с ней модели.</span><span class="sxs-lookup"><span data-stu-id="c8095-105">Processing the structure in the **Mining Structure** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] processes all the associated models.</span></span>  
  
 <span data-ttu-id="c8095-106">Обработка структуры интеллектуального анализа данных производится с помощью следующих средств.</span><span class="sxs-lookup"><span data-stu-id="c8095-106">You can process a mining structure by using these tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
-   <span data-ttu-id="c8095-107">XMLA: команда Process</span><span class="sxs-lookup"><span data-stu-id="c8095-107">XMLA: Process command</span></span>  
  
 <span data-ttu-id="c8095-108">Дополнительные сведения об обработке отдельных моделей см. в разделе [Обработка модели интеллектуального анализа данных](process-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="c8095-108">For information about how to process individual models, see [Process a Mining Model](process-a-mining-model.md).</span></span>  
  
### <a name="to-process-a-mining-structure-and-all-associated-mining-models-using-sql-server-data-tools"></a><span data-ttu-id="c8095-109">Обработка структуры интеллектуального анализа данных и всех связанных с ней моделей интеллектуального анализа данных с помощью SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="c8095-109">To process a mining structure and all associated mining models using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="c8095-110">Выберите пункт **Обработать структуру интеллектуального анализа данных и все модели** из пункта меню **Модель интеллектуального анализа данных** в среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8095-110">Select **Process Mining Structure and All Models** from the **Mining Model** menu item in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
     <span data-ttu-id="c8095-111">При внесении изменений в структуру будет выдано приглашение к повторному развертыванию структуры перед обработкой моделей.</span><span class="sxs-lookup"><span data-stu-id="c8095-111">If you made changes to the structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="c8095-112">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="c8095-112">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="c8095-113">В диалоговом окне **Обработка \<structure> структуры интеллектуального анализа данных** нажмите кнопку **выполнить** .</span><span class="sxs-lookup"><span data-stu-id="c8095-113">Click **Run** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
     <span data-ttu-id="c8095-114">Откроется диалоговое окно **Ход обработки** , отображающее подробные сведения об обработке модели.</span><span class="sxs-lookup"><span data-stu-id="c8095-114">The **Process Progress** dialog box opens to display the details of model processing.</span></span>  
  
3.  <span data-ttu-id="c8095-115">Нажмите кнопку **Закрыть** в диалоговом окне **Ход обработки** после завершения обработки моделей.</span><span class="sxs-lookup"><span data-stu-id="c8095-115">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="c8095-116">В диалоговом окне **Обработка \<structure> структуры интеллектуального анализа данных** нажмите кнопку **Закрыть** .</span><span class="sxs-lookup"><span data-stu-id="c8095-116">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8095-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="c8095-117">See Also</span></span>  
 [<span data-ttu-id="c8095-118">Задачи и инструкции по структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="c8095-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
