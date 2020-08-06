---
title: Проверьте входную подсистему диска на наличие проблем с повторным чтением | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: cedf4097-5b73-4964-9935-74a101847019
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19809b1554e435600eb4eeae424bed17dc27bdbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728226"
---
# <a name="check-disk-input-output-subsystem-for-read-retry-problems"></a><span data-ttu-id="73506-102">Проверка на наличие проблем повторного чтения в подсистеме дискового ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="73506-102">Check Disk Input Output Subsystem for Read Retry Problems</span></span>
  <span data-ttu-id="73506-103">Это правило проверяет журнал событий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на наличие сообщения об ошибке 825.</span><span class="sxs-lookup"><span data-stu-id="73506-103">This rule checks the event log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message 825.</span></span> <span data-ttu-id="73506-104">Это сообщение показывает, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удалось считать данные с диска с первой попытки.</span><span class="sxs-lookup"><span data-stu-id="73506-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was unable to read data from the disk on the first try.</span></span> <span data-ttu-id="73506-105">Оно указывает на серьезную проблему в подсистеме дискового ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="73506-105">This message indicates a major problem with the disk I/O subsystem.</span></span> <span data-ttu-id="73506-106">Это сообщение не указывает на текущую проблему [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73506-106">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem.</span></span> <span data-ttu-id="73506-107">Однако проблема подсистемы дискового ввода-вывода может привести к потере данных или повреждению базы данных, если она не будет решена.</span><span class="sxs-lookup"><span data-stu-id="73506-107">However, the disk problem could cause data loss or database corruption if it is not resolved.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="73506-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="73506-108">Best Practices Recommendations</span></span>  
 <span data-ttu-id="73506-109">Следующие действия помогут обнаружить и исправить базовую проблему оборудования.</span><span class="sxs-lookup"><span data-stu-id="73506-109">The following actions might help you discover and resolve the underlying hardware problem:</span></span>  
  
-   <span data-ttu-id="73506-110">Просмотрите журнал ошибок и переменный текст данного сообщения, объясняющие суть проблемы.</span><span class="sxs-lookup"><span data-stu-id="73506-110">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="73506-111">Проверьте дисковую систему.</span><span class="sxs-lookup"><span data-stu-id="73506-111">Check the disk system.</span></span> <span data-ttu-id="73506-112">Проблема может быть связана с жесткими дисками, контроллерами дисков, контроллерами дисковых массивов или драйверами дисков.</span><span class="sxs-lookup"><span data-stu-id="73506-112">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="73506-113">Обратитесь к производителю диска за новейшими утилитами проверки состояния дисковой системы.</span><span class="sxs-lookup"><span data-stu-id="73506-113">Contact the disk manufacturer for the latest utilities for checking the status of the disk system.</span></span>  
  
-   <span data-ttu-id="73506-114">Обратитесь к производителю диска за новейшими обновлениями драйверов.</span><span class="sxs-lookup"><span data-stu-id="73506-114">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="73506-115">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="73506-115">For More Information</span></span>  
 [<span data-ttu-id="73506-116">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="73506-116">MSSQLSERVER_825</span></span>](../errors-events/mssqlserver-825-database-engine-error.md)  
  
 <span data-ttu-id="73506-117">[Основные операции ввода-вывода в SQL Server, раздел 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="73506-117">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
