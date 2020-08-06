---
title: Конфигурация ядро СУБД-FILESTREAM | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], about FILESTREAM
ms.assetid: 641a10a1-ae52-4d26-8f1c-a032a4aeff02
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab12b507246a3e13ac59be213813604d531d9a28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735906"
---
# <a name="database-engine-configuration---filestream"></a><span data-ttu-id="2c804-102">Настройка компонента Database Engine — Filestream</span><span class="sxs-lookup"><span data-stu-id="2c804-102">Database Engine Configuration - Filestream</span></span>
  <span data-ttu-id="2c804-103">Эта страница используется, чтобы включить FILESTREAM для этой установки [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c804-103">Use this page to enable FILESTREAM for this installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="2c804-104">Файловый поток интегрируется [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] с файловой системой NTFS путем хранения `varbinary(max)` данных больших двоичных объектов (BLOB) в виде файлов в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="2c804-104">FILESTREAM integrates the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with an NTFS file system by storing `varbinary(max)` binary large object (BLOB) data as files on the file system.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="2c804-105">можно вставлять, обновлять, запрашивать, искать и создавать резервные копии данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="2c804-105">statements can insert, update, query, search, and back up FILESTREAM data.</span></span> <span data-ttu-id="2c804-106">Интерфейсы файловой системы Win32 предоставляют потоковый доступ к этим данным.</span><span class="sxs-lookup"><span data-stu-id="2c804-106">Win32 file system interfaces provide streaming access to the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2c804-107">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="2c804-107">UI element list</span></span>  
 <span data-ttu-id="2c804-108">**Разрешить FILESTREAM при доступе через Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="2c804-108">**Enable FILESTREAM for Transact-SQL access**</span></span>  
 <span data-ttu-id="2c804-109">Выберите, чтобы включить FILESTREAM для доступа [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c804-109">Select to enable FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="2c804-110">Необходимо выбрать этот элемент управления, прежде чем будут доступны другие параметры управления.</span><span class="sxs-lookup"><span data-stu-id="2c804-110">This control must be checked before the other control options will be available.</span></span>  
  
 <span data-ttu-id="2c804-111">**Разрешить FILESTREAM при потоковом доступе файлового ввода-вывода**</span><span class="sxs-lookup"><span data-stu-id="2c804-111">**Enable FILESTREAM for file I/O streaming access**</span></span>  
 <span data-ttu-id="2c804-112">Выберите, чтобы разрешить потоковый доступ Win32 для FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="2c804-112">Select to enable Win32 streaming access for FILESTREAM.</span></span>  
  
 <span data-ttu-id="2c804-113">**Имя общего ресурса Windows**</span><span class="sxs-lookup"><span data-stu-id="2c804-113">**Windows share name**</span></span>  
 <span data-ttu-id="2c804-114">Этот элемент управления используется для ввода имени общего ресурса Windows, в котором будут храниться данные FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="2c804-114">Use this control to enter the name of the Windows share in which the FILESTREAM data will be stored.</span></span>  
  
 <span data-ttu-id="2c804-115">**Разрешить удаленным клиентам потоковый доступ к данным FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="2c804-115">**Allow remote clients to have streaming access to FILESTREAM data**</span></span>  
 <span data-ttu-id="2c804-116">Выберите этот элемент управления, чтобы разрешить удаленным клиентам доступ к этим данным FILESTREAM на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="2c804-116">Select this control to allow remote clients to access this FILESTREAM data on this server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c804-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="2c804-117">See Also</span></span>  
 <span data-ttu-id="2c804-118">[Включение и настройка FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="2c804-118">[Enable and Configure FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="2c804-119">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2c804-119">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
