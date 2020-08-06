---
title: Как изменить свойства экземпляра CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7a6c719a-3735-43b7-b3ab-dfadd325eca2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b02785a32fa1f64d5da0c3202acd7916da1e65ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728609"
---
# <a name="how-to-edit-the-cdc-instance-properties"></a><span data-ttu-id="95469-102">Как изменить свойства экземпляра CDC</span><span class="sxs-lookup"><span data-stu-id="95469-102">How to Edit the CDC Instance Properties</span></span>
  <span data-ttu-id="95469-103">Следующая процедура описывает изменение свойств конфигурации экземпляра CDC с помощью консоли конструктора CDC.</span><span class="sxs-lookup"><span data-stu-id="95469-103">This procedure describes how to use the CDC Designer Console to edit the configuration properties for a CDC instance.</span></span>  
  
### <a name="to-edit-the-cdc-instance-configuration-properties"></a><span data-ttu-id="95469-104">Изменение свойств конфигурации экземпляра CDC</span><span class="sxs-lookup"><span data-stu-id="95469-104">To edit the CDC instance configuration properties</span></span>  
  
1.  <span data-ttu-id="95469-105">В меню **Пуск** выберите **Консоль конструктора CDC**.</span><span class="sxs-lookup"><span data-stu-id="95469-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="95469-106">На панели слева разверните узел **Отслеживание измененных данных** , а затем разверните службу, содержащую экземпляр, свойства которого необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="95469-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance with the properties that you want to edit.</span></span>  
  
3.  <span data-ttu-id="95469-107">Выберите имя экземпляра, свойства которого необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="95469-107">Select the name of the instance where you want to edit the properties.</span></span>  
  
4.  <span data-ttu-id="95469-108">На панели «Действия» с правой стороны консоли конструктора CDC щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="95469-108">From the Actions pane on the right side of the CDC Designer Console, click **Properties**.</span></span>  
  
     <span data-ttu-id="95469-109">Можно также щелкнуть правой кнопкой мыши экземпляр, свойства которого необходимо изменить, и выбрать команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="95469-109">You can also right-click the instance where you want to edit the properties and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="95469-110">В редакторе свойств измените свойства на следующих вкладках:</span><span class="sxs-lookup"><span data-stu-id="95469-110">In the Properties editor, edit the properties in the following tabs:</span></span>  
  
    -   <span data-ttu-id="95469-111">**Oracle**. На вкладке **Oracle** в редакторе свойств можно изменить описание, которое было введено на странице создания базы данных CDC в мастере создания экземпляра, а также изменить данные для соединения с базой данных интеллектуального анализа журналов Oracle.</span><span class="sxs-lookup"><span data-stu-id="95469-111">**Oracle**: Use the **Oracle** tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
         <span data-ttu-id="95469-112">Сведения о том, что можно изменить на этой вкладке, приведены в разделе [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="95469-112">For information about what you can edit in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
    -   <span data-ttu-id="95469-113">**Таблицы**. На вкладке **Таблицы** можно изменять таблицы и столбцы, выбранные в базе данных-источнике Oracle.</span><span class="sxs-lookup"><span data-stu-id="95469-113">**Tables**: Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span>  
  
         <span data-ttu-id="95469-114">Сведения о том, что можно изменить на этой вкладке, приведены в разделе [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="95469-114">For information about what you can edit in this tab, see Edit [Edit Tables](edit-tables.md)</span></span>  
  
    -   <span data-ttu-id="95469-115">**Скрипты**. Вкладка **Скрипты** служит для обычного или повторного запуска скрипта в базе данных-источнике Oracle, который настраивает дополнительное журналирование.</span><span class="sxs-lookup"><span data-stu-id="95469-115">**Scripts**: Use the **Scripts** tab to run or re-run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
         <span data-ttu-id="95469-116">Сведения о том, что можно сделать на этой вкладке, приведены в разделе [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span><span class="sxs-lookup"><span data-stu-id="95469-116">For information about what you can do in this tab, see [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span></span>  
  
    -   <span data-ttu-id="95469-117">**Дополнительно**. На вкладке **Дополнительно** можно добавлять особые свойства к экземпляру CDC.</span><span class="sxs-lookup"><span data-stu-id="95469-117">**Advanced**: Use the **Advanced** tab to add special properties to the CDC instance.</span></span>  
  
         <span data-ttu-id="95469-118">Сведения о том, что можно сделать на этой вкладке, приведены в разделе [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="95469-118">For information about what you can do in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
