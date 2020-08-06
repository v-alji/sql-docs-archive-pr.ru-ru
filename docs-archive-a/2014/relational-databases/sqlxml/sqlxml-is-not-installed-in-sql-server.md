---
title: SQLXML не установлен в SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 3dbb4f65-41de-48b8-ad62-47c9d7932de3
author: rothja
ms.author: jroth
ms.openlocfilehash: ffa4cfd8b18dbfd9b4ba05599e2a973ac5f6e888
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665922"
---
# <a name="sqlxml-is-not-installed-in-sql-server"></a><span data-ttu-id="208ee-102">SQLXML не установлен в SQL Server</span><span class="sxs-lookup"><span data-stu-id="208ee-102">SQLXML Is Not Installed in SQL Server</span></span>
  <span data-ttu-id="208ee-103">До версии [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] компонент SQLXML 4.0 распространялся с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и входил в состав установки по умолчанию всех версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], кроме [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="208ee-103">Before [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], SQLXML 4.0 was released with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and was part of the default installation of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versions except for [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="208ee-104">Начиная с [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], последняя версия SQLXML (SQLXML 4.0 с пакетом обновления 1 (SP1)) больше не включается в состав [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="208ee-104">Starting with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the latest version of SQLXML (SQLXML 4.0 SP1) is no longer included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="208ee-105">Чтобы установить SQLXML 4,0 с пакетом обновления 1 (SP1), когда он доступен, скачайте его из [папки установки для SQLXML SP1](https://www.microsoft.com/download/details.aspx?id=44272).</span><span class="sxs-lookup"><span data-stu-id="208ee-105">To install SQLXML 4.0 SP1 when it is available, download it from [Install Location for SQLXML SP1](https://www.microsoft.com/download/details.aspx?id=44272).</span></span>  
  
 <span data-ttu-id="208ee-106">Если приложение выполняется в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и требует SQLXML 4.0, а на компьютере не установлен [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], необходимо загрузить и установить SQLXML 4.0 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="208ee-106">If an application runs on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and requires SQLXML 4.0, and if the computer does not have [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you must download and install SQLXML 4.0 SP1.</span></span>  
  
## <a name="sqlxml-40-sp1-behavior-with-new-data-types-using-sqloledb-and-sql-server-native-client-ole-db-provider"></a><span data-ttu-id="208ee-107">Поведение SQLXML 4.0 при работе с новыми типами данных с помощью SQLOLEDB и поставщика OLE DB для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="208ee-107">SQLXML 4.0 SP1 Behavior with New Data Types Using SQLOLEDB and SQL Server Native Client OLE DB Provider</span></span>  
 <span data-ttu-id="208ee-108">В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] добавлены следующие типы данных, которые могут использовать разработчики, применяющие SQLXML.</span><span class="sxs-lookup"><span data-stu-id="208ee-108">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduces the following data types, which developers using SQLXML might want to use:</span></span>  
  
-   `Date`  
  
-   `Time`  
  
-   `DateTime2`  
  
-   `DateTimeOffset`  
  
 <span data-ttu-id="208ee-109">При использовании SQLXML 4.0 с пакетом обновления 1 (SP1) совместно с SQLOLEDB (из компонентов Windows DAC, ранее известных как компоненты MDAC) или совместно с поставщиком [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OLE DB для собственного клиента [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] эти новые типы будут доступны разработчику в виде строк.</span><span class="sxs-lookup"><span data-stu-id="208ee-109">When using SQLXML 4.0 SP1 with either SQLOLEDB (from Windows Data Access Components, formerly Microsoft Data Access Components) or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], these new types will appear as strings to a developer.</span></span> <span data-ttu-id="208ee-110">SQLXML 4.0 с пакетом обновления 1 (SP1) позволяет использовать эти четыре новых типа данных в качестве встроенных скалярных типов в поставщике OLE DB версии 11.0 для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="208ee-110">SQLXML 4.0 SP1 will enable these four new data types as built-in scalar types when used with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider 11.0.</span></span> <span data-ttu-id="208ee-111">Без загрузки SQLXML 4.0 с пакетом обновления 1 (SP1) при сопоставлении этих типов с нестроковыми типами может происходить усечение и потеря части данных.</span><span class="sxs-lookup"><span data-stu-id="208ee-111">Until you download SQLXML 4.0 SP1, mapping these types to non-string types might cause truncation of some data.</span></span> <span data-ttu-id="208ee-112">Например, сопоставление `DateTime2` с `xsd:date` приведет к усечению данных до [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] `DateTime` точности 3,33 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="208ee-112">For example, mapping `DateTime2` to `xsd:date` will cause data to be truncated to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] `DateTime` precision of 3.33 milliseconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="208ee-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="208ee-113">See Also</span></span>  
 [<span data-ttu-id="208ee-114">Основные понятия о программировании для SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="208ee-114">SQLXML 4.0 Programming Concepts</span></span>](sqlxml-4-0-programming-concepts.md)  
  
  
