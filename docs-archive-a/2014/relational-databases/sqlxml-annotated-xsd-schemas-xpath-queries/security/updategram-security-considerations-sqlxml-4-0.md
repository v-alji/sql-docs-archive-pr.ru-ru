---
title: Вопросы безопасности диаграмма обновления (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, updategrams
- security [SQLXML], updategrams
- updategrams [SQLXML], security
ms.assetid: 00dc6cf4-a2e8-4cca-bdd6-d5122102a82d
author: rothja
ms.author: jroth
ms.openlocfilehash: eb0319285e6e8cf6e8b3e70f3eb6b9923de06f55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666992"
---
# <a name="updategram-security-considerations-sqlxml-40"></a><span data-ttu-id="0cc05-102">Вопросы безопасности диаграмм обновления (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="0cc05-102">Updategram Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="0cc05-103">Ниже приведены рекомендации по безопасному использованию диаграмм обновления.</span><span class="sxs-lookup"><span data-stu-id="0cc05-103">The following are security guidelines for using updategrams:</span></span>  
  
-   <span data-ttu-id="0cc05-104">Рекомендуется избегать использования сопоставления по умолчанию при использовании диаграмм обновления для обновления данных.</span><span class="sxs-lookup"><span data-stu-id="0cc05-104">Avoid using default mapping when you use updategrams to update data.</span></span> <span data-ttu-id="0cc05-105">При использовании сопоставления по умолчанию имя элемента в диаграмме обновления сопоставляется с именем таблицы, а имя атрибута сопоставляется со столбцом.</span><span class="sxs-lookup"><span data-stu-id="0cc05-105">When you use default mapping, an element name in an updategram maps to a table name, and an attribute name maps to a column.</span></span> <span data-ttu-id="0cc05-106">Это представляет собой информацию о таблице базы данных и столбце в базе данных, что может быть потенциальной угрозой безопасности.</span><span class="sxs-lookup"><span data-stu-id="0cc05-106">This exposes the database table and column information in the database, which can be a potential security risk.</span></span> <span data-ttu-id="0cc05-107">Вместо этого при указании отдельной схемы сопоставления, которая сопоставляет элементы и атрибуты в диаграмме обновления с таблицами и столбцами базы данных, имена элементов и атрибутов диаграммы обновления могут иметь произвольную форму, а схема делает необходимое сопоставление этих имен с таблицами и столбцами базы данных.</span><span class="sxs-lookup"><span data-stu-id="0cc05-107">Instead, if you specify a separate mapping schema that maps the elements and attributes in an updategram to the database tables and columns, your updategram element and attribute names can be arbitrary, and the schema does necessary mapping of these names to the database tables and columns.</span></span> <span data-ttu-id="0cc05-108">Таким образом сведения из базы данных не представлены в диаграмме обновления.</span><span class="sxs-lookup"><span data-stu-id="0cc05-108">Thus, the database information is not exposed in an updategram.</span></span>  
  
-   <span data-ttu-id="0cc05-109">Не следует разрешать пользователям создавать и исполнять собственные диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="0cc05-109">Do not allow users to create and execute their updategrams.</span></span> <span data-ttu-id="0cc05-110">Рекомендуется сохранять диаграммы обновления в виде шаблонов на сервере, а не создавать их динамически в приложениях ASP-типа, которые создают риск, имея возможность изменять данные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0cc05-110">It is recommended having updategrams reside as templates on a server rather than creating them dynamically in ASP-type applications, which could put the data in the database at risk.</span></span> <span data-ttu-id="0cc05-111">Можно избежать этого риска, если предоставить пользователям доступ к данным только через диаграммы обновления, представленные в виде шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0cc05-111">Allowing users to access the data only through the updategrams provided as templates, can eliminate this risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc05-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="0cc05-112">See Also</span></span>  
 [<span data-ttu-id="0cc05-113">Использование диаграмм обновления для изменения данных в SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="0cc05-113">Using Updategrams to Modify Data in SQLXML 4.0</span></span>](../updategrams/using-updategrams-to-modify-data-in-sqlxml-4-0.md)  
  
  
