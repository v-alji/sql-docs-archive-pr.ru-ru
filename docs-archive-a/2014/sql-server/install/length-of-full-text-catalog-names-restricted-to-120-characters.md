---
title: Длина имен полнотекстовых каталогов ограничена 120 символами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text catalogs names
ms.assetid: 50633373-83f6-4ed9-99b9-71f92479a14f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fa9b06fa6fe4acd79782c19a8814357721e59c24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669250"
---
# <a name="length-of-full-text-catalog-names-restricted-to-120-characters"></a><span data-ttu-id="b438d-102">Длина имен полнотекстовых каталогов ограничена 120 символами</span><span class="sxs-lookup"><span data-stu-id="b438d-102">Length of full-text catalog names restricted to 120 characters</span></span>
  <span data-ttu-id="b438d-103">Длина имен полнотекстового каталога ограничена 120 символами в отличие от 128 символов в предыдущих версиях служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b438d-103">The length of full-text catalog names is restricted to 120 characters, reduced from the 128 character restriction in previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="description"></a><span data-ttu-id="b438d-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b438d-104">Description</span></span>  
 <span data-ttu-id="b438d-105">Это изменение не влияет на существующие имена каталогов, однако скрипты, создающие полнотекстовые каталоги с именами длиннее 120 символов, завершаются с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b438d-105">This change does not affect existing catalog names; however, scripts that create full-text catalogs with names longer than 120 characters result in an error.</span></span> <span data-ttu-id="b438d-106">Имена каталогов используются для формирования логических имен файлов, соответствующих каталогу.</span><span class="sxs-lookup"><span data-stu-id="b438d-106">The catalog names are used to generate logical file names that correspond to catalogs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b438d-107">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="b438d-107">Corrective Action</span></span>  
 <span data-ttu-id="b438d-108">Следует изменить все скрипты, создающие полнотекстовые каталоги, чтобы длина имен была ограничена 120 символами.</span><span class="sxs-lookup"><span data-stu-id="b438d-108">Modify all scripts that create full-text catalogs to ensure that they restrict catalog names to 120 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b438d-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="b438d-109">See Also</span></span>  
 [<span data-ttu-id="b438d-110">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="b438d-110">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
