---
title: База данных публикации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.publicationdatabase.f1
ms.assetid: a9fafc9b-9963-4b59-97a0-3472158fa665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 511e5f2e2caa934313ba96fb3dbc4cadddace968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655062"
---
# <a name="publication-database"></a><span data-ttu-id="13f6d-102">База данных публикации</span><span class="sxs-lookup"><span data-stu-id="13f6d-102">Publication Database</span></span>
  <span data-ttu-id="13f6d-103">База данных публикации — это база данных на издателе, которая является источником данных и объектов базы данных, предназначенных для репликации.</span><span class="sxs-lookup"><span data-stu-id="13f6d-103">The publication database is the database on the Publisher that is the source of data and database objects to be replicated.</span></span> <span data-ttu-id="13f6d-104">Необходимо задействовать все базы данных публикации, которые будут использоваться в репликации.</span><span class="sxs-lookup"><span data-stu-id="13f6d-104">Each publication database used in replication must be enabled.</span></span> <span data-ttu-id="13f6d-105">База данных задействуется, если элемент предопределенной роли сервера **sysadmin** выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="13f6d-105">The database is enabled when a member of the **sysadmin** fixed server role:</span></span>  
  
-   <span data-ttu-id="13f6d-106">создает публикацию в этой базе данных с помощью мастера создания публикаций;</span><span class="sxs-lookup"><span data-stu-id="13f6d-106">Creates a publication on that database using the New Publication Wizard.</span></span>  
  
-   <span data-ttu-id="13f6d-107">выбирает базу данных в диалоговом окне **Свойства издателя** ;</span><span class="sxs-lookup"><span data-stu-id="13f6d-107">Selects the database in the **Publisher Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="13f6d-108">выполняет процедуру **sp_replicationdboption** и присваивает параметрам **publish** (для моментальных снимков или публикаций транзакций) или **merge publish** (для публикаций слиянием) значение **True**.</span><span class="sxs-lookup"><span data-stu-id="13f6d-108">Executes **sp_replicationdboption** and sets the option **publish** (for snapshot or transactional publications) or **merge publish** (for merge publications) to **True**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="13f6d-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="13f6d-109">Options</span></span>  
 <span data-ttu-id="13f6d-110">**Базы данных**</span><span class="sxs-lookup"><span data-stu-id="13f6d-110">**Databases**</span></span>  
 <span data-ttu-id="13f6d-111">Выберите имя базы данных, содержащее данные и объекты базы данных, которое нужно опубликовать.</span><span class="sxs-lookup"><span data-stu-id="13f6d-111">Select the name of the database that contains the data and database objects that you want to publish.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f6d-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="13f6d-112">See Also</span></span>  
 <span data-ttu-id="13f6d-113">[Публикация данных и объектов базы данных](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="13f6d-113">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="13f6d-114">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="13f6d-114">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="13f6d-115">[Просмотр и изменение свойств издателя и распространителя](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="13f6d-115">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="13f6d-116">sp_replicationdboption (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="13f6d-116">sp_replicationdboption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql)  
  
  
