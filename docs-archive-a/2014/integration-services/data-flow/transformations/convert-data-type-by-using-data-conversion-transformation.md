---
title: Преобразование данных в другой тип данных с помощью преобразования «Конвертация данных» | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: 4aabbe4f-7666-4672-865a-9627bd25fbfd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 878741717c36c18e9a069c62e86be0148272239f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665459"
---
# <a name="convert-data-to-a-different-data-type-by-using-the-data-conversion-transformation"></a><span data-ttu-id="a5ec8-102">Преобразование данных в другой тип данных с помощью преобразования «Конвертация данных»</span><span class="sxs-lookup"><span data-stu-id="a5ec8-102">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>
  <span data-ttu-id="a5ec8-103">Чтобы добавить и настроить преобразование «Конвертация данных», пакет должен обладать как минимум одной задачей потока данных и одним источником.</span><span class="sxs-lookup"><span data-stu-id="a5ec8-103">To add and configure a Data Conversion transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-convert-data-to-a-different-data-type"></a><span data-ttu-id="a5ec8-104">Произведение конвертации данных в другой тип данных</span><span class="sxs-lookup"><span data-stu-id="a5ec8-104">To convert data to a different data type</span></span>  
  
1.  <span data-ttu-id="a5ec8-105">В среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="a5ec8-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="a5ec8-106">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="a5ec8-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a5ec8-107">Щелкните вкладку **Поток данных** и перетащите преобразование «Конвертация данных» из **области элементов**в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="a5ec8-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Data Conversion transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="a5ec8-108">Подключите преобразование «Конвертация данных» к потоку данных, перетащив соединитель из источника или предыдущего преобразования в преобразование «Конвертация данных».</span><span class="sxs-lookup"><span data-stu-id="a5ec8-108">Connect the Data Conversion transformation to the data flow by dragging a connector from the source or the previous transformation to the Data Conversion transformation.</span></span>  
  
5.  <span data-ttu-id="a5ec8-109">Дважды щелкните преобразование «Конвертация данных».</span><span class="sxs-lookup"><span data-stu-id="a5ec8-109">Double-click the Data Conversion transformation.</span></span>  
  
6.  <span data-ttu-id="a5ec8-110">В диалоговом окне **Редактор преобразования "Конвертация данных"** в таблице **Доступные входные столбцы** установите флажки рядом со столбцами, данные из которых необходимо преобразовать.</span><span class="sxs-lookup"><span data-stu-id="a5ec8-110">In the **Data ConversionTransformation Editor** dialog box, in the **Available Input Columns** table, select the check box next to the columns whose data type you want to convert.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5ec8-111">К каждому входному столбцу можно применить несколько преобразований.</span><span class="sxs-lookup"><span data-stu-id="a5ec8-111">You can apply multiple data conversions to an input column.</span></span>  
  
7.  <span data-ttu-id="a5ec8-112">При необходимости измените значение по умолчанию в столбце **Псевдоним вывода** .</span><span class="sxs-lookup"><span data-stu-id="a5ec8-112">Optionally, modify the default values in the **Output Alias** column.</span></span>  
  
8.  <span data-ttu-id="a5ec8-113">Выберите новый тип данных для столбца из списка **Тип данных** .</span><span class="sxs-lookup"><span data-stu-id="a5ec8-113">In the **Data Type** list, select the new data type for the column.</span></span> <span data-ttu-id="a5ec8-114">По умолчанию тип данных является типом данных входного столбца.</span><span class="sxs-lookup"><span data-stu-id="a5ec8-114">The default data type is the data type of the input column.</span></span>  
  
9. <span data-ttu-id="a5ec8-115">Дополнительно, в зависимости от выбранного типа данных, можно обновить значения в столбцах **Длина**, **Точность**, **Масштаб**и **Кодовая страница** .</span><span class="sxs-lookup"><span data-stu-id="a5ec8-115">Optionally, depending on the selected data type, update the values in the **Length**, the **Precision**, the **Scale**, and the **Code Page** columns.</span></span>  
  
10. <span data-ttu-id="a5ec8-116">Для настройки вывода ошибок нажмите **Настройка вывода ошибок**.</span><span class="sxs-lookup"><span data-stu-id="a5ec8-116">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="a5ec8-117">Дополнительные сведения см. в разделе [Настройка вывода ошибок в компоненте потока данных](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a5ec8-117">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="a5ec8-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a5ec8-118">Click **OK**.</span></span>  
  
12. <span data-ttu-id="a5ec8-119">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="a5ec8-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ec8-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="a5ec8-120">See Also</span></span>  
 <span data-ttu-id="a5ec8-121">[Data Conversion Transformation](data-conversion-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="a5ec8-121">[Data Conversion Transformation](data-conversion-transformation.md) </span></span>  
 <span data-ttu-id="a5ec8-122">[Преобразования служб Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="a5ec8-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="a5ec8-123">[Пути служб Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="a5ec8-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="a5ec8-124">[Типы данных служб Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="a5ec8-124">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 [<span data-ttu-id="a5ec8-125">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="a5ec8-125">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
