---
title: Диалоговое окно "Сохранение (запрещено)" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.table.tablerecreatenosave.f1
ms.assetid: 7efda8e3-739f-4c97-a497-b8808a0acbea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19e5f848f20cf74feb3e802e931cbde3aa8d3dc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734862"
---
# <a name="save-not-permitted-dialog-box"></a><span data-ttu-id="6396c-102">Диалоговое окно «Сохранение (запрещено)»</span><span class="sxs-lookup"><span data-stu-id="6396c-102">Save (Not Permitted) Dialog Box</span></span>
  <span data-ttu-id="6396c-103">Диалоговое окно **Сохранение (запрещено)** выдает предупреждение о том, что сохранение невозможно, поскольку выполненные изменения требуют удаления и повторного создания перечисленных таблиц.</span><span class="sxs-lookup"><span data-stu-id="6396c-103">The **Save** (Not Permitted) dialog box warns you that saving changes is not permitted because the changes you have made require the listed tables to be dropped and re-created.</span></span>  
  
 <span data-ttu-id="6396c-104">Повторное создание таблицы может понадобиться для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="6396c-104">The following actions might require a table to be re-created:</span></span>  
  
-   <span data-ttu-id="6396c-105">добавление нового столбца в середину таблицы;</span><span class="sxs-lookup"><span data-stu-id="6396c-105">Adding a new column to the middle of the table</span></span>  
  
-   <span data-ttu-id="6396c-106">удаление столбца;</span><span class="sxs-lookup"><span data-stu-id="6396c-106">Dropping a column</span></span>  
  
-   <span data-ttu-id="6396c-107">изменение допустимости значения NULL для столбца;</span><span class="sxs-lookup"><span data-stu-id="6396c-107">Changing column nullability</span></span>  
  
-   <span data-ttu-id="6396c-108">изменение порядка столбцов;</span><span class="sxs-lookup"><span data-stu-id="6396c-108">Changing the order of the columns</span></span>  
  
-   <span data-ttu-id="6396c-109">изменение типа данных столбца.</span><span class="sxs-lookup"><span data-stu-id="6396c-109">Changing the data type of a column</span></span>  
  
 <span data-ttu-id="6396c-110">Чтобы изменить этот параметр, в меню **Сервис** выберите пункт **Параметры**, разверните **Конструкторы**и щелкните **Конструкторы таблиц и баз данных**.</span><span class="sxs-lookup"><span data-stu-id="6396c-110">To change this option, on the **Tools** menu, click **Options**, expand **Designers**, and then click **Table and Database Designers**.</span></span> <span data-ttu-id="6396c-111">Установите или снимите флажок **Запретить сохранение изменений, требующих повторного создания таблицы** .</span><span class="sxs-lookup"><span data-stu-id="6396c-111">Select or clear the **Prevent saving changes that require the table to be re-created** check box.</span></span>  
  
  
