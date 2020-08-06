---
title: Имена источников данных и 64-разрядные операционные системы | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: c2f86810-2775-4ddd-8df7-e8373785a7fc
author: rothja
ms.author: jroth
ms.openlocfilehash: ae31584ca3c076919f688d1ef9bdef80706c6940
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657072"
---
# <a name="data-source-names-and-64-bit-operating-systems"></a><span data-ttu-id="fb45e-102">Имена источников данных и 64-разрядные операционные системы</span><span class="sxs-lookup"><span data-stu-id="fb45e-102">Data Source Names and 64-Bit Operating Systems</span></span>
  <span data-ttu-id="fb45e-103">Для построения и запуска 32-разрядного приложения в 64-разрядной операционной системе необходимо создать источник данных ODBC с помощью программы администрирования ODBC (исполняемый файл %windir%\SysWOW64\odbcad32.exe).</span><span class="sxs-lookup"><span data-stu-id="fb45e-103">To build and run an application as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb45e-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="fb45e-104">Remarks</span></span>  
 <span data-ttu-id="fb45e-105">В 64-разрядной операционной системе Windows есть два файла odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="fb45e-105">A 64-bit Windows operating system has two odbcad32.exe files:</span></span>  
  
-   <span data-ttu-id="fb45e-106">%SystemRoot%\system32\odbcad32.exe используется для создания и поддержки имен источников данных для 64-разрядных приложений.</span><span class="sxs-lookup"><span data-stu-id="fb45e-106">%SystemRoot%\system32\odbcad32.exe is used to create and maintain data source names for 64-bit applications.</span></span>  
  
-   <span data-ttu-id="fb45e-107">%SystemRoot%\SysWOW64\odbcad32.exe используется для создания и поддержки имен источников данных для 32-разрядных приложений, в том числе и 32-разрядных приложений, работающих на 64-разрядной операционной системе.</span><span class="sxs-lookup"><span data-stu-id="fb45e-107">%SystemRoot%\SysWOW64\odbcad32.exe is used to create and maintain data source names for 32-bit applications, including 32-bit applications that run on 64-bit operating systems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb45e-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="fb45e-108">See Also</span></span>  
 [<span data-ttu-id="fb45e-109">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="fb45e-109">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
