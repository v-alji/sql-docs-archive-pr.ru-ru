---
title: Назначение "Набора записей" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.recordsetdest.f1
helpviewer_keywords:
- Recordset destination
- ADO recordsets [Integration Services]
- destinations [Integration Services], Recordset
- in-memory ADO recordsets [Integration Services]
ms.assetid: be973cf1-c4ff-49f8-987e-314c08ef98e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1acc29c904e9020721e8ac62dff09a8ec29a392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657170"
---
# <a name="recordset-destination"></a><span data-ttu-id="07fc7-102">назначение «Набор записей»</span><span class="sxs-lookup"><span data-stu-id="07fc7-102">Recordset Destination</span></span>
  <span data-ttu-id="07fc7-103">Назначение «Набора записей» создает и заполняет набор записей ADO в памяти.</span><span class="sxs-lookup"><span data-stu-id="07fc7-103">The Recordset destination creates and populates an in-memory ADO recordset.</span></span> <span data-ttu-id="07fc7-104">Форма набора записей определяется входными данными назначения «набор записей» во время проектирования.</span><span class="sxs-lookup"><span data-stu-id="07fc7-104">The shape of the recordset is defined by the input to the Recordset destination at design time.</span></span>  
  
## <a name="configuration-of-the-recordset-destination"></a><span data-ttu-id="07fc7-105">Настройка назначения «Набор записей»</span><span class="sxs-lookup"><span data-stu-id="07fc7-105">Configuration of the Recordset Destination</span></span>  
 <span data-ttu-id="07fc7-106">Назначение «Набор записей» настраивается с помощью указания переменной для хранения набора записей ADO.</span><span class="sxs-lookup"><span data-stu-id="07fc7-106">You configure the Recordset destination by specifying the variable that stores the ADO recordset.</span></span>  
  
 <span data-ttu-id="07fc7-107">Во время выполнения набор записей ADO записывается в переменную типа Object, заданную в свойстве VariableName назначения "Набор записей".</span><span class="sxs-lookup"><span data-stu-id="07fc7-107">At run time, an ADO recordset is written to the variable of type, Object, that is specified in the VariableName property of the Recordset destination.</span></span> <span data-ttu-id="07fc7-108">Переменная делает набор записей доступным за пределами потока данных, где он может быть использован скриптами и другими элементами пакета.</span><span class="sxs-lookup"><span data-stu-id="07fc7-108">The variable then makes the Recordset available outside the data flow, where it can be used by scripts and other package elements.</span></span>  
  
 <span data-ttu-id="07fc7-109">У данного источника один вход.</span><span class="sxs-lookup"><span data-stu-id="07fc7-109">This source has one input.</span></span> <span data-ttu-id="07fc7-110">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="07fc7-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="07fc7-111">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="07fc7-111">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="07fc7-112">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="07fc7-112">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="07fc7-113">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="07fc7-113">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="07fc7-114">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="07fc7-114">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="07fc7-115">Пользовательские свойства назначения «Набор записей»</span><span class="sxs-lookup"><span data-stu-id="07fc7-115">Recordset Destination Custom Properties</span></span>](recordset-destination-custom-properties.md)  
  
 <span data-ttu-id="07fc7-116">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="07fc7-116">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="07fc7-117">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="07fc7-117">Related Tasks</span></span>  
 [<span data-ttu-id="07fc7-118">Использование назначения «Набор записей»</span><span class="sxs-lookup"><span data-stu-id="07fc7-118">Use a Recordset Destination</span></span>](recordset-destination.md)  
  
  
