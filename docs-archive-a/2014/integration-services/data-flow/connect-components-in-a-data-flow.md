---
title: Соединение компонентов в потоке данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 70616a58-8921-4218-85bf-f3e90c5a9dbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8fc4a2fa81e9b110c27ea63b16d835d069bf12cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728574"
---
# <a name="connect-components-in-a-data-flow"></a><span data-ttu-id="89cce-102">Соединение компонентов в потоке данных</span><span class="sxs-lookup"><span data-stu-id="89cce-102">Connect Components in a Data Flow</span></span>
  <span data-ttu-id="89cce-103">Эта процедура описывает способ соединения выхода компонентов в потоке данных с другими компонентами того же потока.</span><span class="sxs-lookup"><span data-stu-id="89cce-103">This procedure describes how to connect the output of components in a data flow to other components within the same data flow.</span></span>  
  
### <a name="to-connect-components-in-a-data-flow"></a><span data-ttu-id="89cce-104">Соединение компонентов в потоке данных</span><span class="sxs-lookup"><span data-stu-id="89cce-104">To connect components in a data flow</span></span>  
  
1.  <span data-ttu-id="89cce-105">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="89cce-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="89cce-106">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="89cce-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="89cce-107">Перейдите на вкладку **Поток управления** , затем дважды щелкните задачу потока данных, содержащую поток данных, в котором требуется соединить компоненты.</span><span class="sxs-lookup"><span data-stu-id="89cce-107">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow in which you want to connect components.</span></span>  
  
4.  <span data-ttu-id="89cce-108">В области конструктора на вкладке **Поток данных** выберите преобразование или источник, который необходимо соединить.</span><span class="sxs-lookup"><span data-stu-id="89cce-108">On the design surface of the **Data Flow** tab, select the transformation or source that you want to connect.</span></span>  
  
5.  <span data-ttu-id="89cce-109">Перетащите зеленую стрелку выхода преобразования или источника на преобразование или целевой объект.</span><span class="sxs-lookup"><span data-stu-id="89cce-109">Drag the green output arrow of a transformation or a source to a transformation or to a destination.</span></span> <span data-ttu-id="89cce-110">Некоторые компоненты потока данных могут иметь вывод ошибок, который можно соединять аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="89cce-110">Some data flow components have error outputs that you can connect in the same way.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="89cce-111">Некоторые компоненты потока данных могут иметь несколько выходов; следовательно, можно подключить каждый выход к отдельному преобразованию или целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="89cce-111">Some data flow components can have multiple outputs and you can connect each output to a different transformation or destination.</span></span>  
  
6.  <span data-ttu-id="89cce-112">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="89cce-112">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89cce-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="89cce-113">See Also</span></span>  
 <span data-ttu-id="89cce-114">[Добавление или удаление компонента в потоке данных](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="89cce-114">[Add or Delete a Component in a Data Flow](data-flow.md) </span></span>  
 <span data-ttu-id="89cce-115">[Настройка вывода ошибок в компоненте потока данных](../configure-an-error-output-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="89cce-115">[Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="89cce-116">Поток данных</span><span class="sxs-lookup"><span data-stu-id="89cce-116">Data Flow</span></span>](data-flow.md)  
  
  
