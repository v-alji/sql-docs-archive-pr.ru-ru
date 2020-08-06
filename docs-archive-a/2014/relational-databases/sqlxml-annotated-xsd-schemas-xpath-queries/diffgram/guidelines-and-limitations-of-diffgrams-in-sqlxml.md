---
title: Рекомендации и ограничения дельтами в SQLXML | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: cf8689c4-2a63-4d05-b202-21b5ff187d7f
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f2901f02f8b4a8fc7b77dcb6c1cb166cb6af6ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664820"
---
# <a name="guidelines-and-limitations-of-diffgrams-in-sqlxml"></a><span data-ttu-id="f299d-102">Рекомендации и действующие ограничения SQLXML, связанные с дельтами</span><span class="sxs-lookup"><span data-stu-id="f299d-102">Guidelines and Limitations of DiffGrams in SQLXML</span></span>
  <span data-ttu-id="f299d-103">При использовании дельт с SQLXML 4.0 учитывайте следующее.</span><span class="sxs-lookup"><span data-stu-id="f299d-103">Remember the following when using DiffGrams with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="f299d-104">Типы больших двоичных объектов (BLOB), например `text/ntext` и изображения, не следует использовать в блоке `<diffgr:before>` при работе с дельтами, поскольку в этом случае они будут включены в управление параллелизмом.</span><span class="sxs-lookup"><span data-stu-id="f299d-104">Binary large object (BLOB) types like `text/ntext` and images should not be used in the `<diffgr:before>` block in when working with DiffGrams, because this will include them for use in concurrency control.</span></span> <span data-ttu-id="f299d-105">Это может вызвать проблемы в работе [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] из-за ограничений, налагаемых на сравнение для типов больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="f299d-105">This can cause problems with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="f299d-106">Например, ключевое слово LIKE используется в предложении WHERE для сравнения столбцов типа данных `text`; однако, в случае с типами больших двоичных объектов, когда размер данных превышает 8 КБ, такое сравнение завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f299d-106">For example, the LIKE keyword is used in the WHERE clause for comparing between columns of the `text` data type; however, comparisons will fail in the case of BLOB types where the size of the data is greater than 8K.</span></span>  
  
-   <span data-ttu-id="f299d-107">Специальные символы в данных типа `ntext` могут вызывать проблемы в работе SQLXML 4.0 из-за ограничений, налагаемых на сравнение типов больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="f299d-107">Special characters in `ntext` data can cause problems with SQLXML 4.0 because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="f299d-108">Например, использование «[Serializable]» в блоке `<diffgr:before>` DiffGram при проверке параллелизма столбца с типом `ntext` завершится ошибкой со следующим описанием ошибки SQLOLEDB:</span><span class="sxs-lookup"><span data-stu-id="f299d-108">For example, the use of "[Serializable]" in the `<diffgr:before>` block of a DiffGram when used in concurrency checking of a column of `ntext` type will fail with the following SQLOLEDB error description:</span></span>  
  
    ```  
    Empty update, no updatable rows found   Transaction aborted  
    ```  
  
  
