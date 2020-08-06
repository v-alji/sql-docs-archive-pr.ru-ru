---
title: Выбор направления потока CDC в соответствии с типом изменения | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3afa531e-f425-40a4-a1bf-1c3e1727287e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a9b4e0c6a196669e4cedafcecf0477b228f3001
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657205"
---
# <a name="direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="03558-102">Выбор направления потока CDC в соответствии с типом изменения</span><span class="sxs-lookup"><span data-stu-id="03558-102">Direct the CDC Stream According to the Type of Change</span></span>
  <span data-ttu-id="03558-103">Чтобы можно было добавить и настроить преобразование «Разделитель CDC», пакет должен содержать по крайней мере одну задачу «Поток данных» и источник CDC.</span><span class="sxs-lookup"><span data-stu-id="03558-103">To add and configure a CDC splitter Transformation, the package must contain at least one Data Flow task and a CDC source.</span></span>  
  
 <span data-ttu-id="03558-104">Для источника CDC, добавленного к пакету, должен быть выбран режим обработки NetCDC.</span><span class="sxs-lookup"><span data-stu-id="03558-104">The CDC source added to the package must have a NetCDC processing mode selected.</span></span> <span data-ttu-id="03558-105">Дополнительные сведения о выборе режимов обработки см. в разделе [Редактор источника "CDC" (страница "Диспетчер соединений")](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="03558-105">For more information on selecting processing modes, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
### <a name="to-direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="03558-106">Выбор направления потока CDC в соответствии с типом изменения</span><span class="sxs-lookup"><span data-stu-id="03558-106">To direct the CDC stream according to the type of change</span></span>  
  
1.  <span data-ttu-id="03558-107">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]откройте проект служб [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="03558-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="03558-108">В Обозревателе решений дважды щелкните пакет, чтобы его открыть.</span><span class="sxs-lookup"><span data-stu-id="03558-108">In the Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="03558-109">Щелкните вкладку **Поток данных** , а затем **Панель инструментов**перетащите разделитель CDC в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="03558-109">Click the **Data Flow** tab, and then from the **Toolbox**, drag the CDC splitter to the design surface.</span></span>  
  
4.  <span data-ttu-id="03558-110">Установите соединение источника CDC, который включен в пакет, с разделителем CDC.</span><span class="sxs-lookup"><span data-stu-id="03558-110">Connect the CDC source that is included in the package to the CDC Splitter.</span></span>  
  
5.  <span data-ttu-id="03558-111">Установите соединение разделителя CDC с одним или несколькими назначениями.</span><span class="sxs-lookup"><span data-stu-id="03558-111">Connect the CDC splitter to one or more destinations.</span></span> <span data-ttu-id="03558-112">Предусмотрена возможность подключить до трех различных выводов.</span><span class="sxs-lookup"><span data-stu-id="03558-112">You can connect up to three different outputs.</span></span>  
  
6.  <span data-ttu-id="03558-113">Выберите один из следующих выводов.</span><span class="sxs-lookup"><span data-stu-id="03558-113">Select one of the following outputs:</span></span>  
  
    -   <span data-ttu-id="03558-114">Вывод удаления. Вывод, в который направляются строки изменения DELETE.</span><span class="sxs-lookup"><span data-stu-id="03558-114">Delete output: The output where DELETE change rows are directed.</span></span>  
  
    -   <span data-ttu-id="03558-115">Вывод вставки. Вывод, в который направляются строки изменения INSERT.</span><span class="sxs-lookup"><span data-stu-id="03558-115">Insert output: The output where INSERT change rows are directed.</span></span>  
  
    -   <span data-ttu-id="03558-116">Вывод обновления. Вывод, в который направляются строки перед и после изменения UPDATE и строки изменения Merge.</span><span class="sxs-lookup"><span data-stu-id="03558-116">Update output: The output where before/after UPDATE change rows and Merge change rows are directed.</span></span>  
  
7.  <span data-ttu-id="03558-117">Кроме того, можно настроить дополнительные свойства, используя диалоговое окно **Расширенный редактор** .</span><span class="sxs-lookup"><span data-stu-id="03558-117">Optionally, you can configure the advanced properties using the **Advanced Editor** dialog box.</span></span>  
  
     <span data-ttu-id="03558-118">Диалоговое окно **Расширенный редактор** содержит свойства, которые могут быть заданы программным путем.</span><span class="sxs-lookup"><span data-stu-id="03558-118">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
     <span data-ttu-id="03558-119">Открытие диалогового окна **Расширенный редактор** .</span><span class="sxs-lookup"><span data-stu-id="03558-119">To open the **Advanced Editor** dialog box:</span></span>  
  
    -   <span data-ttu-id="03558-120">На экране **Поток данных** вашего проекта [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] щелкните правой кнопкой мыши разделитель CDC и выберите элемент **Показать расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="03558-120">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
     <span data-ttu-id="03558-121">Дополнительные сведения об использовании разделителя CDC см. в разделе «Компоненты CDC для служб Microsoft SQL Server Integration Services».</span><span class="sxs-lookup"><span data-stu-id="03558-121">For more information about using the CDC splitter see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03558-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="03558-122">See Also</span></span>  
 [<span data-ttu-id="03558-123">Разделитель CDC</span><span class="sxs-lookup"><span data-stu-id="03558-123">CDC Splitter</span></span>](cdc-splitter.md)  
  
  
