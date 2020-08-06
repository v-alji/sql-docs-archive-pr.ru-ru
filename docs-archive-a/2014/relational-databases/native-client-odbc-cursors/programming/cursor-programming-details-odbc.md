---
title: Сведения о программировании курсора (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- ODBC cursors, programming
- cursors [ODBC], programming
ms.assetid: 6bae29c4-7f49-419c-8712-90db734f992e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4108e195c16d321578a70852dd990f4f8d658832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657775"
---
# <a name="cursor-programming-details-odbc"></a><span data-ttu-id="5d736-102">Подробные сведения о программировании курсоров (ODBC)</span><span class="sxs-lookup"><span data-stu-id="5d736-102">Cursor Programming Details (ODBC)</span></span>
  <span data-ttu-id="5d736-103">Выбор правильного типа курсора может повысить производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="5d736-103">Choosing the correct cursor type can improve application performance.</span></span> <span data-ttu-id="5d736-104">При определенных условиях [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] может неявно преобразовать тип курсора при выполнении инструкции SQL, которая не поддерживается типом запрашиваемого курсора.</span><span class="sxs-lookup"><span data-stu-id="5d736-104">Under certain conditions, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may implicitly convert a cursor type when you execute an SQL statement that is not supported by the cursor type you requested.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d736-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="5d736-105">In This Section</span></span>  
  
-   [<span data-ttu-id="5d736-106">Неявные преобразования курсоров &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="5d736-106">Implicit Cursor Conversions &#40;ODBC&#41;</span></span>](implicit-cursor-conversions-odbc.md)  
  
-   [<span data-ttu-id="5d736-107">Использование автоматической выборки с помощью курсоров ODBC</span><span class="sxs-lookup"><span data-stu-id="5d736-107">Using Autofetch with ODBC Cursors</span></span>](using-autofetch-with-odbc-cursors.md)  
  
-   [<span data-ttu-id="5d736-108">Однопроходные курсоры &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="5d736-108">Fast Forward-Only Cursors &#40;ODBC&#41;</span></span>](fast-forward-only-cursors-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="5d736-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d736-109">See Also</span></span>  
 [<span data-ttu-id="5d736-110">Использование курсоров &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="5d736-110">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  
