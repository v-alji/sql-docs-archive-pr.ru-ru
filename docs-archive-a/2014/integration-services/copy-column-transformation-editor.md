---
title: Редактор преобразования "Копирование столбца" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copymaptransformation.f1
helpviewer_keywords:
- Copy Column Transformation Editor
ms.assetid: d8e70541-d563-4ce4-bf66-bc888a0d3026
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7647d25891b37e5f09356d427072e84b45882e4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665055"
---
# <a name="copy-column-transformation-editor"></a><span data-ttu-id="1bf0c-102">редактор преобразования «Копирование столбца»</span><span class="sxs-lookup"><span data-stu-id="1bf0c-102">Copy Column Transformation Editor</span></span>
  <span data-ttu-id="1bf0c-103">Диалоговое окно **Редактор преобразования «Копирование столбцов»** используется для выбора копируемых столбцов и присвоения имен новым выходным столбцам.</span><span class="sxs-lookup"><span data-stu-id="1bf0c-103">Use the **Copy Column Transformation Editor** dialog box to select columns to copy and to assign names for the new output columns.</span></span>  
  
 <span data-ttu-id="1bf0c-104">Дополнительные сведения о редакторе преобразований «Копирование столбцов» см. в разделе [Copy Column Transformation](data-flow/transformations/copy-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="1bf0c-104">To learn more about the Copy Column transformation, see [Copy Column Transformation](data-flow/transformations/copy-column-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bf0c-105">При простом копировании всех данных из источника в назначение использовать преобразование «Копирование столбцов» необязательно.</span><span class="sxs-lookup"><span data-stu-id="1bf0c-105">When you are simply copying all of your source data to a destination, it may not be necessary to use the Copy Column transformation.</span></span> <span data-ttu-id="1bf0c-106">В некоторых ситуациях можно напрямую соединить источник с назначением, если преобразование данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="1bf0c-106">In some scenarios, you can connect a source directly to a destination, when no data transformation is required.</span></span> <span data-ttu-id="1bf0c-107">В некоторых ситуациях часто бывает предпочтительнее использовать мастер импорта и экспорта SQL Server, который создаст пакет.</span><span class="sxs-lookup"><span data-stu-id="1bf0c-107">In these circumstances it is often preferable to use the SQL Server Import and Export Wizard to create your package for you.</span></span> <span data-ttu-id="1bf0c-108">Позже пакет можно расширить и изменить его конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="1bf0c-108">Later you can enhance and reconfigure the package as needed.</span></span> <span data-ttu-id="1bf0c-109">Дополнительные сведения см. в разделе [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="1bf0c-109">For more information, see [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1bf0c-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="1bf0c-110">Options</span></span>  
 <span data-ttu-id="1bf0c-111">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="1bf0c-111">**Available Input Columns**</span></span>  
 <span data-ttu-id="1bf0c-112">Выберите копируемые столбцы с помощью флажков.</span><span class="sxs-lookup"><span data-stu-id="1bf0c-112">Select columns to copy by using the check boxes.</span></span> <span data-ttu-id="1bf0c-113">Выбранные столбцы добавляются в качестве входных столбцов в таблицу, представленную ниже.</span><span class="sxs-lookup"><span data-stu-id="1bf0c-113">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="1bf0c-114">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="1bf0c-114">**Input Column**</span></span>  
 <span data-ttu-id="1bf0c-115">Выберите столбцы для копирования из списка доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="1bf0c-115">Select columns to copy from the list of available input columns.</span></span> <span data-ttu-id="1bf0c-116">Выбранные столбцы обозначаются флажками в таблице **Доступные входные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="1bf0c-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="1bf0c-117">**Псевдоним вывода**</span><span class="sxs-lookup"><span data-stu-id="1bf0c-117">**Output Alias**</span></span>  
 <span data-ttu-id="1bf0c-118">Введите псевдоним для каждого нового выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="1bf0c-118">Type an alias for each new output column.</span></span> <span data-ttu-id="1bf0c-119">По умолчанию, используется **Копия**и далее имя входного столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="1bf0c-119">The default is **Copy of**, followed by the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bf0c-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="1bf0c-120">See Also</span></span>  
 [<span data-ttu-id="1bf0c-121">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="1bf0c-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
