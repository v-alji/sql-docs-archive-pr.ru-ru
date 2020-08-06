---
title: Задание значения CHECKSUM для параметра базы данных PAGE_VERIFY | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 686b9a4a-ea61-4263-9ab8-f444a3077679
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13296a976722390668b8ca6d901cf0dd080e5cc3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749735"
---
# <a name="set-the-page_verify-database-option-to-checksum"></a><span data-ttu-id="91e35-102">Задание значения CHECKSUM для параметра базы данных PAGE_VERIFY</span><span class="sxs-lookup"><span data-stu-id="91e35-102">Set the PAGE_VERIFY Database Option to CHECKSUM</span></span>
  <span data-ttu-id="91e35-103">Это правило проверяет, имеет ли параметр базы данных PAGE_VERIFY значение CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="91e35-103">This rule checks whether PAGE_VERIFY database option is set to CHECKSUM.</span></span> <span data-ttu-id="91e35-104">Если для параметра базы данных PAGE_VERIFY указано значение CHECKSUM, компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] рассчитывает контрольную сумму для содержимого страницы в целом и сохраняет значение в заголовке страницы при записи страницы на диск.</span><span class="sxs-lookup"><span data-stu-id="91e35-104">When CHECKSUM is enabled for the PAGE_VERIFY database option, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] calculates a checksum over the contents of the whole page, and stores the value in the page header when a page is written to disk.</span></span> <span data-ttu-id="91e35-105">При считывании страницы с диска контрольная сумма вычисляется повторно и сравнивается со значением из заголовка.</span><span class="sxs-lookup"><span data-stu-id="91e35-105">When the page is read from disk, the checksum is recomputed and compared to the checksum value that is stored in the page header.</span></span> <span data-ttu-id="91e35-106">Это помогает обеспечить высокий уровень целостности данных в файлах.</span><span class="sxs-lookup"><span data-stu-id="91e35-106">This helps provide a high level of data-file integrity.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="91e35-107">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="91e35-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="91e35-108">Присвойте параметру базы данных PAGE_VERIFY значение CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="91e35-108">Set the PAGE_VERIFY database option to CHECKSUM.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="91e35-109">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="91e35-109">For More Information</span></span>  
 [<span data-ttu-id="91e35-110">Параметры ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="91e35-110">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
  
