---
title: Как просмотреть свойства экземпляра CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bce9b82-7bbd-41df-b3f4-4b40b8bad474
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 86fa298b0e02a16ddbaea220ef7f3d9f6172bf85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732881"
---
# <a name="how-to-view-the-cdc-instance-properties"></a><span data-ttu-id="1045b-102">Как просмотреть свойства экземпляра CDC</span><span class="sxs-lookup"><span data-stu-id="1045b-102">How to View the CDC Instance Properties</span></span>
  <span data-ttu-id="1045b-103">Эта процедура описывает использование консоли конструктора CDC для просмотра сведений об экземплярах, создаваемых для поддержки управления работой экземпляров.</span><span class="sxs-lookup"><span data-stu-id="1045b-103">This procedure describes how to use the CDC Designer Console to view information about the instances that you create to help manage the operation of the instances.</span></span>  
  
### <a name="to-view-information-about-a-specific-instance"></a><span data-ttu-id="1045b-104">Просмотр сведений об определенном экземпляре</span><span class="sxs-lookup"><span data-stu-id="1045b-104">To view information about a specific instance</span></span>  
  
1.  <span data-ttu-id="1045b-105">В меню **Пуск** выберите **Консоль конструктора CDC**.</span><span class="sxs-lookup"><span data-stu-id="1045b-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="1045b-106">На панели слева разверните узел **Отслеживание измененных данных** , а затем разверните службу, содержащую экземпляр, данные которого необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="1045b-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="1045b-107">Выберите имя нужного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1045b-107">Select the name of an instance you want to work with.</span></span>  
  
     <span data-ttu-id="1045b-108">Сведения об экземпляре будут отображены в центральной части консоли конструктора CDC.</span><span class="sxs-lookup"><span data-stu-id="1045b-108">The information about the instance is displayed in the center part of the CDC Designer Console.</span></span> <span data-ttu-id="1045b-109">Сведения разделены на четыре вкладки.</span><span class="sxs-lookup"><span data-stu-id="1045b-109">It is divided into four tabs.</span></span> <span data-ttu-id="1045b-110">Все вкладки доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1045b-110">All of the tabs are read only.</span></span>  
  
     <span data-ttu-id="1045b-111">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="1045b-111">**Status**</span></span>  
     <span data-ttu-id="1045b-112">На этой вкладке отображаются сведения о текущем состоянии отслеживания измененных данных для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1045b-112">This tab displays the information about the current status of the change data capture for the instance.</span></span> <span data-ttu-id="1045b-113">Сведения о том, что отображено на этой вкладке, приведены в пункте **Вкладки средства просмотра** раздела [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="1045b-113">For information about what is displayed in this tab, see the **Viewer Tabs** section in [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
     <span data-ttu-id="1045b-114">**Oracle**</span><span class="sxs-lookup"><span data-stu-id="1045b-114">**Oracle**</span></span>  
     <span data-ttu-id="1045b-115">На этой вкладке отображаются общие сведения об экземпляре CDC и базе данных-источнике Oracle.</span><span class="sxs-lookup"><span data-stu-id="1045b-115">This tab displays general information about the CDC instance and the Oracle source database.</span></span> <span data-ttu-id="1045b-116">Сведения о том, что отображено на этой вкладке, приведены в разделе [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1045b-116">For information about what is displayed in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
     <span data-ttu-id="1045b-117">**Таблицы**</span><span class="sxs-lookup"><span data-stu-id="1045b-117">**Tables**</span></span>  
     <span data-ttu-id="1045b-118">На этой вкладке отображаются сведения о таблицах, включенных в отслеживание измененных данных.</span><span class="sxs-lookup"><span data-stu-id="1045b-118">This tab displays information about the tables included in the change data capture.</span></span> <span data-ttu-id="1045b-119">На ней также указаны столбцы, состояние которых отслеживается.</span><span class="sxs-lookup"><span data-stu-id="1045b-119">It also lists the columns that are captured.</span></span> <span data-ttu-id="1045b-120">Сведения о том, что отображено на этой вкладке, приведены в разделе [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="1045b-120">For information about what is displayed in this tab, see [Edit Tables](edit-tables.md).</span></span>  
  
     <span data-ttu-id="1045b-121">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="1045b-121">**Advanced**</span></span>  
     <span data-ttu-id="1045b-122">На этой вкладке приведен список дополнительных свойств, которые задаются в редакторе свойств.</span><span class="sxs-lookup"><span data-stu-id="1045b-122">This tab displays a list of advanced properties that you define in the properties editor.</span></span> <span data-ttu-id="1045b-123">Сведения о том, что отображено на этой вкладке, приведены в разделе [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1045b-123">For information about what is displayed in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
