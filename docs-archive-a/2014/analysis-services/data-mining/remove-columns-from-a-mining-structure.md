---
title: Удалить столбцы из структуры интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- removing columns
- deleting columns
- columns [data mining], mining structure columns
ms.assetid: 41073ffe-9351-416b-9f0c-62634bc213f9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ad1de08d57d00fd9798e1ceeddb85d146d7111
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654606"
---
# <a name="remove-columns-from-a-mining-structure"></a><span data-ttu-id="ece97-102">удалить столбцы из структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ece97-102">Remove Columns from a Mining Structure</span></span>
  <span data-ttu-id="ece97-103">Конструктор интеллектуального анализа данных можно использовать для удаления столбцов структуры интеллектуального анализа данных после ее создания.</span><span class="sxs-lookup"><span data-stu-id="ece97-103">You can use Data Mining Designer to remove columns from a mining structure after the structure has already been created.</span></span> <span data-ttu-id="ece97-104">Возможны следующие причины удаления столбца структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ece97-104">Reasons to remove a mining structure column might include the following:</span></span>  
  
-   <span data-ttu-id="ece97-105">Структура интеллектуального анализа данных содержит несколько копий столбца, и вы хотите избежать дублирования данных в модели.</span><span class="sxs-lookup"><span data-stu-id="ece97-105">The mining structure contains multiple copies of a column and you want to avoid the use of duplicate data in a model.</span></span>  
  
-   <span data-ttu-id="ece97-106">Данные должны быть защищены, но детализация была разрешена.</span><span class="sxs-lookup"><span data-stu-id="ece97-106">The data should be protected, but drillthrough has been enabled.</span></span>  
  
-   <span data-ttu-id="ece97-107">Данные не используются в моделировании и не должны обрабатываться.</span><span class="sxs-lookup"><span data-stu-id="ece97-107">The data is unused in modeling and should not be processed.</span></span>  
  
 <span data-ttu-id="ece97-108">При удалении столбца из структуры интеллектуального анализа данных не производится его удаления из представления источников данных или внешних данных. Удаляются только метаданные.</span><span class="sxs-lookup"><span data-stu-id="ece97-108">Deleting a column from the mining structure does not change the column in the data source view or in the external data; only metadata is deleted.</span></span> <span data-ttu-id="ece97-109">Однако при изменении столбцов, используемых в структуре интеллектуального анализа данных, необходимо выполнить повторную обработку структуры и любых, основанных на ней моделей.</span><span class="sxs-lookup"><span data-stu-id="ece97-109">However, when you change the columns used in a mining structure, you must reprocess the structure and any models based on it.</span></span>  
  
### <a name="to-remove-a-column-from-the-mining-structure"></a><span data-ttu-id="ece97-110">Удаление столбца из структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ece97-110">To remove a column from the mining structure</span></span>  
  
1.  <span data-ttu-id="ece97-111">Перейдите на вкладку **Структура интеллектуального анализа данных** в конструкторе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ece97-111">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="ece97-112">Разверните дерево для структуры интеллектуального анализа данных для отображения всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="ece97-112">Expand the tree for the mining structure, to show all the columns.</span></span>  
  
3.  <span data-ttu-id="ece97-113">Щелкните правой кнопкой мыши столбец, который необходимо удалить, а затем выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ece97-113">Right-click the column that you want to delete, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="ece97-114">В диалоговом окне **Удаление объектов** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ece97-114">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece97-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="ece97-115">See Also</span></span>  
 [<span data-ttu-id="ece97-116">Задачи и инструкции по структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ece97-116">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
