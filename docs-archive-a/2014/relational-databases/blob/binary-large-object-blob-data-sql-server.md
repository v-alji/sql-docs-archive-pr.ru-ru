---
title: Данные большого двоичного объекта (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], design and implementation
ms.assetid: 97509274-c3f8-43e5-a37c-52f1ffe0961a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a663dedf34d75a21ee8df6b97979548c04abf7ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667246"
---
# <a name="binary-large-object-blob-data-sql-server"></a><span data-ttu-id="47343-102">Данные большого двоичного объекта (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="47343-102">Binary Large Object (Blob) Data (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="47343-103">имеет решения для хранения файлов и документов в базе данных или на удаленных устройствах хранения.</span><span class="sxs-lookup"><span data-stu-id="47343-103">provides solutions for storing files and documents in the database or on remote storage devices.</span></span>  
  
##  <a name="in-this-section"></a><a name="section"></a> <span data-ttu-id="47343-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="47343-104">In This Section</span></span>  
 [<span data-ttu-id="47343-105">Сравнение параметров для хранения больших двоичных объектов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="47343-105">Compare Options for Storing Blobs &#40;SQL Server&#41;</span></span>](compare-options-for-storing-blobs-sql-server.md)  
 <span data-ttu-id="47343-106">Сравнение преимуществ FILESTREAM, таблиц FileTable и удаленного хранилища больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="47343-106">Compare the advantages of FILESTREAM, FileTables, and Remote Blob Store.</span></span>  
  
 [<span data-ttu-id="47343-107">FILESTREAM (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="47343-107">FILESTREAM &#40;SQL Server&#41;</span></span>](filestream-sql-server.md)  
 <span data-ttu-id="47343-108">FILESTREAM позволяет приложениям на основе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]хранить в файловой системе неструктурированные данные, например документы и изображения.</span><span class="sxs-lookup"><span data-stu-id="47343-108">FILESTREAM enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-based applications to store unstructured data, such as documents and images, on the file system.</span></span> <span data-ttu-id="47343-109">Приложения могут одновременно использовать многопоточные API-интерфейсы и производительность файловой системы, тем самым обеспечивая транзакционную согласованность между неструктурированными и соответствующими им структурированными данными.</span><span class="sxs-lookup"><span data-stu-id="47343-109">Applications can leverage the rich streaming APIs and performance of the file system and at the same time maintain transactional consistency between the unstructured data and corresponding structured data.</span></span>  
  
 [<span data-ttu-id="47343-110">FileTables (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="47343-110">FileTables &#40;SQL Server&#41;</span></span>](filetables-sql-server.md)  
 <span data-ttu-id="47343-111">Функция FileTable обеспечивает поддержку пространства имен файлов Windows и совместимость с приложениями Windows для файлов данных, хранящихся в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47343-111">The FileTable feature brings support for the Windows file namespace and compatibility with Windows applications to the file data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="47343-112">Таблица FileTable позволяет приложению интегрировать свои компоненты хранения и управления данными, а также обеспечивает работу интегрированных служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , включая полнотекстовый и семантический поиск, с неструктурированными данными и метаданными.</span><span class="sxs-lookup"><span data-stu-id="47343-112">FileTable lets an application integrate its storage and data management components, and provides integrated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services - including full-text search and semantic search - over unstructured data and metadata.</span></span>  
  
 <span data-ttu-id="47343-113">Иными словами, появляется возможность хранить файлы и документы в специальных таблицах на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , называемых таблицами FileTable, но при этом доступ к ним возможен из приложений Windows без внесения каких-либо изменений в эти приложения, как если бы они хранились в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="47343-113">In other words, you can store files and documents in special tables in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] called FileTables, but access them from Windows applications as if they were stored in the file system, without making any changes to your client applications.</span></span>  
  
 [<span data-ttu-id="47343-114">Удаленное хранилище больших двоичных объектов (RBS) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="47343-114">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](remote-blob-store-rbs-sql-server.md)  
 <span data-ttu-id="47343-115">Удаленное хранилище больших двоичных объектов для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] позволяет администраторам баз данных сохранять большие двоичные объекты в отдельных хранилищах вместо хранения прямо на сервере.</span><span class="sxs-lookup"><span data-stu-id="47343-115">Remote BLOB store (RBS) for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lets database administrators store binary large objects (BLOBs) in commodity storage solutions instead of directly on the server.</span></span> <span data-ttu-id="47343-116">При этом значительно экономится место на диске и дорогостоящие аппаратные ресурсы сервера.</span><span class="sxs-lookup"><span data-stu-id="47343-116">This saves a significant amount of space and avoids wasting expensive server hardware resources.</span></span> <span data-ttu-id="47343-117">Для удаленного хранилища больших двоичных объектов имеется набор API-библиотек, определяющих стандартизированную модель для приложений, осуществляющих доступ к данным BLOB.</span><span class="sxs-lookup"><span data-stu-id="47343-117">RBS provides a set of API libraries that define a standardized model for applications to access BLOB data.</span></span> <span data-ttu-id="47343-118">Кроме того, в RBS реализованы средства обслуживания, например сборка мусора, что позволяет более эффективно управлять удаленными данными больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="47343-118">RBS also includes maintenance tools, such as garbage collection, to help manage remote BLOB data.</span></span>  
  
 <span data-ttu-id="47343-119">Хранилище RBS включено в установочный носитель [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , но не устанавливается программой установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="47343-119">RBS is included on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media, but is not installed by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program.</span></span>  
  
  
