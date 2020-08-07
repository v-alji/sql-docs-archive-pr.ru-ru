---
title: Добавление или удаление компонента в потоке данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding components
- components [Integration Services], data flow
ms.assetid: d99124f9-0994-4f40-a48e-fdca6a4383e7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f041258d2b66e7b8da540a842848ebf70f4ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729674"
---
# <a name="add-or-delete-a-component-in-a-data-flow"></a><span data-ttu-id="61370-102">Добавление или удаление компонента в потоке данных</span><span class="sxs-lookup"><span data-stu-id="61370-102">Add or Delete a Component in a Data Flow</span></span>
  <span data-ttu-id="61370-103">Компонентами потока данных являются источники, назначения и преобразования потока данных.</span><span class="sxs-lookup"><span data-stu-id="61370-103">Data flow components are sources, destinations, and transformations in a data flow.</span></span> <span data-ttu-id="61370-104">Чтобы добавлять компоненты к потоку данных, необходимо включить задачу потока данных в поток управления пакета.</span><span class="sxs-lookup"><span data-stu-id="61370-104">Before you can add components to a data flow, the control flow in the package must include a Data Flow task.</span></span>  
  
 <span data-ttu-id="61370-105">Следующие процедуры описывают способы добавления или удаления компонента в потоке данных пакета.</span><span class="sxs-lookup"><span data-stu-id="61370-105">The following procedures describe how to add or delete a component in the data flow of a package.</span></span>  
  
### <a name="to-add-a-component-to-a-data-flow"></a><span data-ttu-id="61370-106">Добавление компонента к потоку данных</span><span class="sxs-lookup"><span data-stu-id="61370-106">To add a component to a data flow</span></span>  
  
1.  <span data-ttu-id="61370-107">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="61370-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="61370-108">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="61370-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="61370-109">Откройте вкладку **Поток управления** , а затем дважды щелкните задачу потока данных, содержащую поток данных, к которому необходимо добавить компонент.</span><span class="sxs-lookup"><span data-stu-id="61370-109">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow to which you want to add a component.</span></span>  
  
4.  <span data-ttu-id="61370-110">В инструментарии разверните **Источники потока данных**, **Преобразования потока данных**или **Назначения потока данных**и перетащите элемент потока данных в область конструктора на вкладке **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="61370-110">In the Toolbox, expand **Data Flow Sources**, **Data Flow Transformations**, or **Data Flow Destinations**, and then drag a data flow item to the design surface of the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="61370-111">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="61370-111">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-component-from-a-data-flow"></a><span data-ttu-id="61370-112">Удаление компонента из потока данных</span><span class="sxs-lookup"><span data-stu-id="61370-112">To delete a component from a data flow</span></span>  
  
1.  <span data-ttu-id="61370-113">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="61370-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="61370-114">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="61370-114">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="61370-115">Перейдите на вкладку **Поток управления** и дважды щелкните задачу потока данных, содержащую поток данных, из которого необходимо удалить компонент.</span><span class="sxs-lookup"><span data-stu-id="61370-115">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow from which you want to delete a component.</span></span>  
  
4.  <span data-ttu-id="61370-116">Щелкните правой кнопкой мыши компонент потока данных и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="61370-116">Right-click the data flow component, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="61370-117">Подтвердите операцию удаления.</span><span class="sxs-lookup"><span data-stu-id="61370-117">Confirm the delete operation.</span></span>  
  
6.  <span data-ttu-id="61370-118">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="61370-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61370-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="61370-119">See Also</span></span>  
 <span data-ttu-id="61370-120">[Соединение компонентов в потоке данных](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="61370-120">[Connect Components in a Data Flow](data-flow.md) </span></span>  
 <span data-ttu-id="61370-121">[Настройка вывода ошибок в компоненте потока данных](../configure-an-error-output-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="61370-121">[Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="61370-122">Поток данных</span><span class="sxs-lookup"><span data-stu-id="61370-122">Data Flow</span></span>](data-flow.md)  
  
  
