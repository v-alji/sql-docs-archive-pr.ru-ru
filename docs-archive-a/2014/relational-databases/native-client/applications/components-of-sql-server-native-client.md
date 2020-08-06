---
title: Компоненты SQL Server Native Client | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], components
- components [SQL Server Native Client]
- SQLNCLI, about SQL Server Native Client
ms.assetid: 65f932d5-daa1-4eff-b6df-ee633fcf2a7c
author: rothja
ms.author: jroth
ms.openlocfilehash: 32438b9fb5473d9251acd0aceddb46db373f3548
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665297"
---
# <a name="components-of-sql-server-native-client"></a><span data-ttu-id="dde93-102">Компоненты собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="dde93-102">Components of SQL Server Native Client</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="dde93-103">Native Client содержит следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="dde93-103">Native Client contains the following components:</span></span>  
  
|<span data-ttu-id="dde93-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="dde93-104">Component</span></span>|<span data-ttu-id="dde93-105">Описание</span><span class="sxs-lookup"><span data-stu-id="dde93-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dde93-106">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="dde93-106">sqlncli11.dll</span></span>|<span data-ttu-id="dde93-107">Файл динамически подключаемой библиотеки (DLL), включающий все функциональные возможности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="dde93-107">The dynamic-link library (DLL) file that contains all of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client functionality.</span></span> <span data-ttu-id="dde93-108">В его состав входят поставщик OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client и драйвер ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="dde93-108">This includes the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>|  
|<span data-ttu-id="dde93-109">sqlnclir11.rll</span><span class="sxs-lookup"><span data-stu-id="dde93-109">sqlnclir11.rll</span></span>|<span data-ttu-id="dde93-110">Соответствующий файл ресурса для библиотеки [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="dde93-110">The accompanying resource file for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library.</span></span>|  
|<span data-ttu-id="dde93-111">s10ch_sqlncli.chm</span><span class="sxs-lookup"><span data-stu-id="dde93-111">s10ch_sqlncli.chm</span></span>|<span data-ttu-id="dde93-112">Файл справки мастера источников данных, описывающий, как создавать источник данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], использовать драйвер ODBC собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или поставщик OLE DB собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dde93-112">The Data Source Wizard help file that documents how to create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data source using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>|  
|<span data-ttu-id="dde93-113">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="dde93-113">sqlncli.h</span></span>|<span data-ttu-id="dde93-114">Файл заголовка собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], который содержит все определения, необходимые для использования собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dde93-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header file that contains all of the new definitions needed in order to use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="dde93-115">Этот файл заголовка заменяет оба файла заголовков — odbcss.h и the sqloledb.h.</span><span class="sxs-lookup"><span data-stu-id="dde93-115">This header file replaces both the odbcss.h and the sqloledb.h header files.</span></span> <span data-ttu-id="dde93-116">**Примечание.**  В той же программе нельзя ссылаться на SQLNCLI. h и ODBC. h, но можно ссылаться на SQLNCLI. h и SQLOLEDB. h в той же программе, если только SQLOLEDB. h определен первым.</span><span class="sxs-lookup"><span data-stu-id="dde93-116">**Note:**  You cannot reference sqlncli.h and odbcss.h in the same program, but you can reference sqlncli.h and sqloledb.h in same program as long as sqloledb.h is defined first.</span></span>|  
|<span data-ttu-id="dde93-117">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="dde93-117">sqlncli11.lib</span></span>|<span data-ttu-id="dde93-118">Файл библиотеки, необходимый для непосредственного вызова функций программы **bcp** , которые являются частью [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвера ODBC для собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="dde93-118">The library file needed to directly call the **bcp** utility functions that are part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="dde93-119">**Примечание.**  Если вы ссылаетесь на файл sqlncli11. lib в программном коде, необходимо убедиться, что файл sqlncli11.dll находится в системном пути, и в системном пути пользователей, которые используют ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="dde93-119">**Note:**  If you do reference the sqlncli11.lib file in your programming code, you need to make sure that the sqlncli11.dll file is in your system path, and in the system path of the users that make use of your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dde93-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="dde93-120">See Also</span></span>  
 [<span data-ttu-id="dde93-121">Построение приложений с использованием SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="dde93-121">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
