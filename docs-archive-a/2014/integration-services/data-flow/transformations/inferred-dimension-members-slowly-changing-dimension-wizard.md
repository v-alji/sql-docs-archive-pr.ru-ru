---
title: Выводимые элементы измерения (мастер медленно изменяющихся измерений) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.inferrdim.f1
ms.assetid: 809e395f-2e10-48ff-8860-56403f130628
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dda4345b91c69b134516baab2e5ba9b9990bd6af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667317"
---
# <a name="inferred-dimension-members-slowly-changing-dimension-wizard"></a><span data-ttu-id="69dec-102">Выводимые элементы измерения (мастер медленно изменяющихся измерений)</span><span class="sxs-lookup"><span data-stu-id="69dec-102">Inferred Dimension Members (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="69dec-103">Диалоговое окно **Выводимые элементы измерения** используется для задания параметров их вывода.</span><span class="sxs-lookup"><span data-stu-id="69dec-103">Use the **Inferred Dimension Members** dialog box to specify options for using inferred members.</span></span> <span data-ttu-id="69dec-104">Выводимые элементы существуют в случае, когда таблица фактов ссылается на еще не загруженные элементы таблицы измерения.</span><span class="sxs-lookup"><span data-stu-id="69dec-104">Inferred members exist when a fact table references dimension members that are not yet loaded.</span></span> <span data-ttu-id="69dec-105">При загрузке данных для выводимого элемента можно просто обновить существующую запись, а не создавать ее заново.</span><span class="sxs-lookup"><span data-stu-id="69dec-105">When data for the inferred member is loaded, you can update the existing record rather than create a new one.</span></span>  
  
 <span data-ttu-id="69dec-106">Дополнительные сведения о работе этого мастера см. в разделе [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="69dec-106">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="69dec-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="69dec-107">Options</span></span>  
 <span data-ttu-id="69dec-108">**Включить поддержку выводимых элементов измерения**</span><span class="sxs-lookup"><span data-stu-id="69dec-108">**Enable inferred member support**</span></span>  
 <span data-ttu-id="69dec-109">В случае включения выводимых элементов, необходимо выбрать один из двух следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="69dec-109">If you choose to enable inferred members, you must select one of the two options that follow.</span></span>  
  
 <span data-ttu-id="69dec-110">**Все столбцы с типом изменения имеют значение NULL**</span><span class="sxs-lookup"><span data-stu-id="69dec-110">**All columns with a change type are null**</span></span>  
 <span data-ttu-id="69dec-111">Позволяет указать, вводить ли значения NULL во все столбцы с типом изменения в новой записи выводимых элементов.</span><span class="sxs-lookup"><span data-stu-id="69dec-111">Specify whether to enter null values in all columns with a change type in the new inferred member record.</span></span>  
  
 <span data-ttu-id="69dec-112">**Использовать логический столбец для указания принадлежности текущей записи к выводимым элементам**</span><span class="sxs-lookup"><span data-stu-id="69dec-112">**Use a Boolean column to indicate whether the current record is an inferred member**</span></span>  
 <span data-ttu-id="69dec-113">Позволяет задать, использовать ли существующий логический столбец для указания, является ли текущая запись выводимым элементом.</span><span class="sxs-lookup"><span data-stu-id="69dec-113">Specify whether to use an existing Boolean column to indicate whether the current record is an inferred member.</span></span>  
  
 <span data-ttu-id="69dec-114">**Признак выводимого элемента**</span><span class="sxs-lookup"><span data-stu-id="69dec-114">**Inferred member indicator**</span></span>  
 <span data-ttu-id="69dec-115">Если выбрано использовать логический столбец для указания выводимых элементов как описано выше, выберите столбец из списка.</span><span class="sxs-lookup"><span data-stu-id="69dec-115">If you have chosen to use a Boolean column to indicate inferred members as described above, select the column from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69dec-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="69dec-116">See Also</span></span>  
 [<span data-ttu-id="69dec-117">Настройка выходов с помощью мастера медленно изменяющихся измерений</span><span class="sxs-lookup"><span data-stu-id="69dec-117">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
